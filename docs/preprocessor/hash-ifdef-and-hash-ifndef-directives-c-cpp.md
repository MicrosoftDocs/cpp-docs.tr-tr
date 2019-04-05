---
title: '#ıfdef ve #ifndef yönergeleri (C/C++)'
ms.date: 11/04/2016
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
ms.openlocfilehash: d7a6a1604df03f0607f33e42880270cbdcd62e8b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027236"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef ve #ifndef Yönergeleri (C/C++)
**#İfdef** ve **#ifndef** yönergeleri aynı görevi gerçekleştirmek `#if` ile kullanıldığında yönergesi **tanımlanan**( *tanımlayıcısı* ).

## <a name="syntax"></a>Sözdizimi

```
#ifdef identifier
#ifndef identifier

// equivalent to
#if defined identifier
#if !defined identifier
```

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz **#ifdef** ve **#ifndef** yönergeleri her yerde `#if` kullanılabilir. **#İfdef** *tanımlayıcı* deyimi, `#if 1` olduğunda *tanımlayıcı* tanımlı ve eşdeğerdir `#if 0` olduğunda *tanımlayıcı* tanımlanmadı veya ile tanımlanmamış `#undef` yönergesi. Bu yönergeler yalnızca olup olmadığını denetleyin veya ile tanımlanan tanımlayıcıların devamsızlık `#define`, C veya C++ kaynak koduyla bildirilmiş olan tanımlayıcıları denetlemez.

Bu yönergeler yalnızca dilin önceki sürümleriyle uyumluluk için sağlanır. **Tanımlanan (** *tanımlayıcı* **)** sabit ifade ile kullanılan `#if` yönergesi, tercih edilen yöntemdir.

**#İfndef** yönergesi tarafından denetlenen koşulun tersini denetler **#ifdef**. Tanımlayıcı tanımlı değilse (veya tanımı ile kaldırılmış `#undef`), koşul true (sıfırdan farklı). Aksi halde koşul false (0).

**Microsoft'a Özgü**

*Tanımlayıcı* kullanılarak komut satırından geçirilebilir `/D` seçeneği. En fazla 30 makro belirtilebilir `/D`.

Bu, komut satırından bir tanım iletilebildiği bir tanımı mevcut olup olmadığını denetlemek için yararlıdır. Örneğin:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)