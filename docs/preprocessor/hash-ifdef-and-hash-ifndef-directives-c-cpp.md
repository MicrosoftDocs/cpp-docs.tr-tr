---
description: 'Hakkında daha fazla bilgi edinin: #ifdef ve #ifndef yönergeleri (C/C++)'
title: '##ifdef ve #ifndef yönergeleri (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#ifndef'
- '#ifdef'
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
ms.openlocfilehash: 4888e4516b57465974d99b1c9e8e6393e02f68c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269295"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef ve #ifndef yönergeleri (C/C++)

**#İfdef** ve **#ifndef** yönergeleri, **tanımlı** işleçle birlikte kullanıldığında [#if](hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) yönergesiyle aynı etkiye sahiptir.

## <a name="syntax"></a>Syntax

> **#ifdef** *tanımlayıcı*\
> **#ifndef** *tanımlayıcı*

Bu yönergeler şu şekilde eşdeğerdir:

> **#if tanımlı** *tanımlayıcı*\
> **#if! tanımlı** *tanımlayıcı*

## <a name="remarks"></a>Açıklamalar

**#İfdef** ve **#ifndef** yönergelerini kullanılabilir her yerde kullanabilirsiniz `#if` . Tanımlayıcı tanımlandığında **#ifdef** *tanımlayıcı* ifade eşdeğerdir `#if 1` .  `#if 0` *Tanımlayıcı* tanımlanmadığında veya yönerge tarafından tanımsız olarak eşdeğerdir `#undef` . Bu yönergeler, `#define` C veya C++ kaynak kodunda belirtilen tanımlayıcılar için değil, ile tanımlanan tanımlayıcıların varlığını veya yokluğunu denetler.

Bu yönergeler yalnızca dilin önceki sürümleriyle uyumluluk için sağlanır. Yönergeyle birlikte kullanılan **tanımlı (** *tanımlayıcı* **)** sabit ifade `#if` tercih edilir.

**#İfndef** yönergesi, **#ifdef** tarafından denetlenen koşulun tersini denetler. Tanımlayıcı tanımlanmamışsa veya tanımı ile kaldırılmışsa `#undef` , koşul true (sıfır dışında) olur. Aksi takdirde, koşul false (0) olur.

**Microsoft'a Özgü**

*Tanımlayıcı* , [/d](../build/reference/d-preprocessor-definitions.md) seçeneği kullanılarak komut satırından geçirilebilir. İle en fazla 30 makro belirtilebilir `/D` .

**#İfdef** yönergesi, bir tanımın bir tanım olup olmadığını denetlemek için yararlıdır, çünkü komut satırından bir tanım geçirilebilirler. Örneğin:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
