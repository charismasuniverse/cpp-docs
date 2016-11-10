---
title: "Precedence and Order of Evaluation"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "associativity of operators [C++]"
  - "precedence [C++], operators"
  - "data binding [C++], operator precedence"
  - "operators [C++], precedence"
ms.assetid: 201f7864-0c51-4c55-9d6f-39c5d013bcb0
caps.latest.revision: 8
ms.author: "mithom"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Precedence and Order of Evaluation
The precedence and associativity of C operators affect the grouping and evaluation of operands in expressions. An operator's precedence is meaningful only if other operators with higher or lower precedence are present. Expressions with higher-precedence operators are evaluated first. Precedence can also be described by the word "binding." Operators with a higher precedence are said to have tighter binding.  
  
 The following table summarizes the precedence and associativity (the order in which the operands are evaluated) of C operators, listing them in order of precedence from highest to lowest. Where several operators appear together, they have equal precedence and are evaluated according to their associativity. The operators in the table are described in the sections beginning with [Postfix Operators](../c/postfix-operators.md). The rest of this section gives general information about precedence and associativity.  
  
### Precedence and Associativity of C Operators  
  
|Symbol1|Type of Operation|Associativity|  
|-------------|-----------------------|-------------------|  
|**[ ] ( ) . –>** postfix `++` and postfix **––**|Expression|Left to right|  
|prefix `++` and prefix **–– sizeof &   \*   + – ~ !**|Unary|Right to left|  
|*typecasts*|Unary|Right to left|  
|**\* / %**|Multiplicative|Left to right|  
|**+ –**|Additive|Left to right|  
|**<\< >>**|Bitwise shift|Left to right|  
|**\< > \<= >=**|Relational|Left to right|  
|**== !=**|Equality|Left to right|  
|**&**|Bitwise-AND|Left to right|  
|**^**|Bitwise-exclusive-OR|Left to right|  
|**&#124;**|Bitwise-inclusive-OR|Left to right|  
|**&&**|Logical-AND|Left to right|  
|`&#124;&#124;`|Logical-OR|Left to right|  
|**? :**|Conditional-expression|Right to left|  
|**= \*= /= %=**<br /><br /> **+= –= <\<= >>=&=**<br /><br /> **^= &#124;=**|Simple and compound assignment2|Right to left|  
|**,**|Sequential evaluation|Left to right|  
  
 1. Operators are listed in descending order of precedence. If several operators appear on the same line or in a group, they have equal precedence.  
  
 2. All simple and compound-assignment operators have equal precedence.  
  
 An expression can contain several operators with equal precedence. When several such operators appear at the same level in an expression, evaluation proceeds according to the associativity of the operator, either from right to left or from left to right. The direction of evaluation does not affect the results of expressions that include more than one multiplication (**\***), addition (**+**), or binary-bitwise (**& &#124; ^**) operator at the same level. Order of operations is not defined by the language. The compiler is free to evaluate such expressions in any order, if the compiler can guarantee a consistent result.  
  
 Only the sequential-evaluation (**,**), logical-AND (**&&**), logical-OR (`||`), conditional-expression (**? :**), and function-call operators constitute sequence points and therefore guarantee a particular order of evaluation for their operands. The function-call operator is the set of parentheses following the function identifier. The sequential-evaluation operator (**,**) is guaranteed to evaluate its operands from left to right. (Note that the comma operator in a function call is not the same as the sequential-evaluation operator and does not provide any such guarantee.) For more information, see [Sequence Points](../c/c-sequence-points.md).  
  
 Logical operators also guarantee evaluation of their operands from left to right. However, they evaluate the smallest number of operands needed to determine the result of the expression. This is called "short-circuit" evaluation. Thus, some operands of the expression may not be evaluated. For example, in the expression  
  
```  
x && y++  
```  
  
 the second operand, `y++`, is evaluated only if `x` is true (nonzero). Thus, `y` is not incremented if `x` is false (0).  
  
 **Examples**  
  
 The following list shows how the compiler automatically binds several sample expressions:  
  
|Expression|Automatic Binding|  
|----------------|-----------------------|  
|`a & b &#124;&#124; c`|`(a & b) &#124;&#124; c`|  
|`a = b &#124;&#124; c`|`a = (b &#124;&#124; c)`|  
|`q && r &#124;&#124; s--`|`(q && r) &#124;&#124; s––`|  
  
 In the first expression, the bitwise-AND operator (`&`) has higher precedence than the logical-OR operator (`||`), so `a & b` forms the first operand of the logical-OR operation.  
  
 In the second expression, the logical-OR operator (`||`) has higher precedence than the simple-assignment operator (`=`), so `b || c` is grouped as the right-hand operand in the assignment. Note that the value assigned to `a` is either 0 or 1.  
  
 The third expression shows a correctly formed expression that may produce an unexpected result. The logical-AND operator (`&&`) has higher precedence than the logical-OR operator (`||`), so `q && r` is grouped as an operand. Since the logical operators guarantee evaluation of operands from left to right, `q && r` is evaluated before `s––`. However, if `q && r` evaluates to a nonzero value, `s––` is not evaluated, and `s` is not decremented. If not decrementing `s` would cause a problem in your program, `s––` should appear as the first operand of the expression, or `s` should be decremented in a separate operation.  
  
 The following expression is illegal and produces a diagnostic message at compile time:  
  
|Illegal Expression|Default Grouping|  
|------------------------|----------------------|  
|`p == 0 ? p += 1: p += 2`|`( p == 0 ? p += 1 : p ) += 2`|  
  
 In this expression, the equality operator (`==`) has the highest precedence, so `p == 0` is grouped as an operand. The conditional-expression operator (`? :`) has the next-highest precedence. Its first operand is `p == 0`, and its second operand is `p += 1`. However, the last operand of the conditional-expression operator is considered to be `p` rather than `p += 2`, since this occurrence of `p` binds more closely to the conditional-expression operator than it does to the compound-assignment operator. A syntax error occurs because `+= 2` does not have a left-hand operand. You should use parentheses to prevent errors of this kind and produce more readable code. For example, you could use parentheses as shown below to correct and clarify the preceding example:  
  
```  
( p == 0 ) ? ( p += 1 ) : ( p += 2 )  
```  
  
## See Also  
 [C Operators](../c/c-operators.md)