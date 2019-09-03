---
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
ms.openlocfilehash: 433076388f3646b19d75a907c6b2254098096688
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220108"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef ve #ifndef yönergeleri (C/C++)

**#İfdef** ve **#ifndef** yönergeleri, **tanımlı** işleçle birlikte kullanıldığında [#if](hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) yönergesiyle aynı etkiye sahiptir.

## <a name="syntax"></a>Sözdizimi

> **#ifdef** *tanımlayıcı*\
> **#ifndef** *tanımlayıcı*

Bu yönergeler şu şekilde eşdeğerdir:

> **#if tanımlı** *tanımlayıcı*\
> **#if! tanımlı** *tanımlayıcı*

## <a name="remarks"></a>Açıklamalar

**#İfdef** ve **#ifndef** yönergelerini kullanılabilir her yerde `#if` kullanabilirsiniz. *Tanımlayıcı* tanımlandığında **#ifdef** *tanımlayıcı* ifade eşdeğerdir `#if 1` . *Tanımlayıcı* tanımlanmadığında `#undef` veya `#if 0` yönerge tarafından tanımsız olarak eşdeğerdir. Bu yönergeler, C veya `#define` C++ kaynak kodunda belirtilen tanımlayıcılar için değil, ile tanımlanan tanımlayıcıların varlığını veya yokluğunu denetler.

Bu yönergeler yalnızca dilin önceki sürümleriyle uyumluluk için sağlanır. `#if` Yönergeyle birlikte kullanılan **tanımlı (** *tanımlayıcı* **)** sabit ifade tercih edilir.

**#İfndef** yönergesi, **#ifdef**tarafından denetlenen koşulun tersini denetler. Tanımlayıcı tanımlanmamışsa veya tanımı ile `#undef`kaldırılmışsa, koşul true (sıfır dışında) olur. Aksi takdirde, koşul false (0) olur.

**Microsoft 'a özgü**

*Tanımlayıcı* , [/d](../build/reference/d-preprocessor-definitions.md) seçeneği kullanılarak komut satırından geçirilebilir. İle `/D`en fazla 30 makro belirtilebilir.

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

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)
