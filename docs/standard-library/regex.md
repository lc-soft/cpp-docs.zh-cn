---
title: '&lt;regex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 3e3f3b49b3672042e0376e7738a8cf8924e1c2a8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451450"
---
# <a name="ltregexgt"></a>&lt;regex&gt;

定义一个模板类来分析[正则表达式 (C++)](../standard-library/regular-expressions-cpp.md)，以及定义多个模板类和函数来在文本中搜索正则表达式对象的匹配项。

## <a name="syntax"></a>语法

```cpp
#include <regex>
```

## <a name="remarks"></a>备注

若要创建正则表达式对象，请将模板类 [basic_regex 类](../standard-library/basic-regex-class.md)或其专用化（[regex](../standard-library/regex-typedefs.md#regex) 和[wregex](../standard-library/regex-typedefs.md#wregex)）之一与类型为 [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type) 的语法标志一起使用。

若要在文本中搜索正则表达式对象的匹配项, 请将模板函数[regex_match](../standard-library/regex-functions.md#regex_match)和[regex_search](../standard-library/regex-functions.md#regex_search)与类型[regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)的匹配标志一起使用。 这些函数通过将模板类 [match_results 类](../standard-library/match-results-class.md)及其专用化（[cmatch](../standard-library/regex-typedefs.md#cmatch)、[wcmatch](../standard-library/regex-typedefs.md#wcmatch)、[smatch](../standard-library/regex-typedefs.md#smatch) 和 [wsmatch](../standard-library/regex-typedefs.md#wsmatch)）与模板类 [sub_match 类](../standard-library/sub-match-class.md)及其专用化（[csub_match](../standard-library/regex-typedefs.md#csub_match)、[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)、[ssub_match](../standard-library/regex-typedefs.md#ssub_match) 和 [wssub_match](../standard-library/regex-typedefs.md#wssub_match)）一起使用来返回结果。

若要替换匹配正则表达式对象的文本, 请将模板函数[regex_replace](../standard-library/regex-functions.md#regex_replace)与类型[regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)的匹配标志一起使用。

若要循环访问正则表达式对象的多个匹配项，请将模板类 [regex_iterator 类](../standard-library/regex-iterator-class.md)和 [regex_token_iterator 类](../standard-library/regex-token-iterator-class.md)或其专用化之一（[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)、[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)、[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)、[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)、[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)、[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)、[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)或 [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)）与类型 [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type) 的匹配项标志一起使用。

若要修改正则表达式语法的详细信息，请编写一个实现正则表达式特征的类。

### <a name="classes"></a>类

|类|描述|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|包装正则表达式。|
|[match_results](../standard-library/match-results-class.md)|包含一系列子匹配项。|
|[regex_constants](../standard-library/regex-constants-class.md)|包含各种类型的常量。|
|[regex_error](../standard-library/regex-error-class.md)|报告错误的正则表达式。|
|[regex_iterator](../standard-library/regex-iterator-class.md)|循环访问匹配结果。|
|[regex_traits](../standard-library/regex-traits-class.md)|描述用于匹配的元素的特征。|
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|描述用于匹配的**char**的特征。|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|描述用于匹配的**wchar_t**的特征。|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|循环访问子匹配项。|
|[sub_match](../standard-library/sub-match-class.md)|介绍子匹配项。|

### <a name="type-definitions"></a>类型定义

|||
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)| Char`match_results`的类型定义。|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)| Char`regex_iterator`的类型定义。|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)| Char`regex_token_iterator`的类型定义。|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)| Char`sub_match`的类型定义。|
|[regex](../standard-library/regex-typedefs.md#regex)| Char`basic_regex`的类型定义。|
|[smatch](../standard-library/regex-typedefs.md#smatch)|`string` `match_results` 的类型定义。|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|`string` `regex_iterator` 的类型定义。|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|`string` `regex_token_iterator` 的类型定义。|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|`string` `sub_match` 的类型定义。|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)| Wchar_t`match_results`的类型定义。|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)| Wchar_t`regex_iterator`的类型定义。|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)| Wchar_t`regex_token_iterator`的类型定义。|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)| Wchar_t`sub_match`的类型定义。|
|[wregex](../standard-library/regex-typedefs.md#wregex)| Wchar_t`basic_regex`的类型定义。|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|`wstring` `match_results` 的类型定义。|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|`wstring` `regex_iterator` 的类型定义。|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|`wstring` `regex_token_iterator` 的类型定义。|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|`wstring` `sub_match` 的类型定义。|

### <a name="functions"></a>函数

|函数|描述|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|与正则表达式完全匹配。|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|替换匹配正则表达式。|
|[regex_search](../standard-library/regex-functions.md#regex_search)|搜索正则表达式匹配项。|
|[swap](../standard-library/regex-functions.md#swap)|交换 `basic_regex` 或 `match_results` 对象。|

### <a name="operators"></a>运算符

|运算符|描述|
|-|-|
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|比较各种对象，相等。|
|[operator!=](../standard-library/regex-operators.md#op_neq)|比较各种对象，不相等。|
|[operator<](../standard-library/regex-operators.md#op_lt)|比较各种对象，小于。|
|[operator\<=](../standard-library/regex-operators.md#op_gt_eq)|比较各种对象，小于或等于。|
|[operator>](../standard-library/regex-operators.md#op_gt)|比较各种对象，大于。|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|比较各种对象，大于或等于。|
|[operator<<](../standard-library/regex-operators.md#op_lt_lt)|将 `sub_match` 插入流中。|

## <a name="see-also"></a>请参阅

[正则表达式C++()](../standard-library/regular-expressions-cpp.md)\
[regex_constants 类](../standard-library/regex-constants-class.md)\
[regex_error 类](../standard-library/regex-error-class.md)\
[\<regex > 函数](../standard-library/regex-functions.md)\
[regex_iterator 类](../standard-library/regex-iterator-class.md)\
[\<regex > 运算符](../standard-library/regex-operators.md)\
[regex_token_iterator 类](../standard-library/regex-token-iterator-class.md)\
[regex_traits 类](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
