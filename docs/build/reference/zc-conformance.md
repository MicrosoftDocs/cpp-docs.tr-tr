---
title: /Zc (Uyumluluk)
description: /ZC uyumluluk derleyicisi seçenekleri, uyumlu veya geriye dönük bir davranış için desteği etkinleştirir veya devre dışı bırakır.
ms.date: 09/10/2020
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 13e06cd75f1ee684c2ee1ad6239aeb77b805675e
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041529"
---
# <a name="zc-conformance"></a>`/Zc` Uyumsuzlu

**`/Zc`** Standart veya Microsoft 'a özgü derleyici davranışını belirtmek için derleyici seçeneklerini kullanabilirsiniz.

## <a name="syntax"></a>Syntax

> **`/Zc:`**_seçenek_{,_seçenek_}

## <a name="remarks"></a>Açıklamalar

Visual Studio C veya C++ ' a bir uzantısı standart ile uyumlu olmayan bir şekilde uygulamışsa, **`/Zc`** standart uyumlu veya Microsoft 'a özgü davranışları belirtmek için bir uyumluluk seçeneği kullanabilirsiniz. Bazı seçenekler için, Microsoft 'a özgü davranış, var olan koddaki büyük ölçekli önemli değişikliklere engel olmak için varsayılandır. Diğer durumlarda, varsayılan olarak, güvenlik, performans veya uyumlulukta iyileştirmeler, önemli olmayan değişikliklerin maliyetlerine aykırı olan standart davranıştır. Her uygunluk seçeneğinin varsayılan ayarı, Visual Studio 'nun daha yeni sürümlerinde değişebilir. Her uygunluk seçeneği hakkında daha fazla bilgi için, ilgili seçeneğe yönelik konuya bakın. [`/permissive-`](permissive-standards-conformance.md)Derleyici seçeneği, varsayılan olarak ayarlı olmayan uygunluk seçeneklerini uyumlu ayarlarına örtülü olarak ayarlar.

**`/Zc`** Derleyici seçenekleri şunlardır:

| Seçenek | Davranış |
|--|--|
| [`/Zc:alignedNew`](zc-alignednew.md) | C++ 17 üzerinde hizalanmış dinamik ayırmayı etkinleştirin (varsayılan olarak, C++ 17 ' de). |
| [`/Zc:auto`](zc-auto-deduce-variable-type.md) | İçin yeni standart C++ anlamını zorla **`auto`** (varsayılan olarak açık). |
| [`/Zc__cplusplus`](zc-cplusplus.md) | `__cplusplus`Desteklenen standardı (varsayılan olarak kapalı) raporlamak için makroyu etkinleştirin. |
| [`/Zc:externConstexpr`](zc-externconstexpr.md) | Değişkenler için dış bağlantıları etkinleştirin **`constexpr`** (varsayılan olarak kapalıdır). |
| [`/Zc:forScope`](zc-forscope-force-conformance-in-for-loop-scope.md) | Standart C++ **`for`** kapsam kurallarını zorla (varsayılan olarak açık). |
| [`/ZcimplicitNoexcept`](zc-implicitnoexcept-implicit-exception-specifiers.md) | Gerekli işlevlerde örtük ' i etkinleştirin **`noexcept`** (varsayılan olarak açık). |
| [`/Zc:inline`](zc-inline-remove-unreferenced-comdat.md) | Başvurulmayan işlevi veya verileri COMDAT ise veya yalnızca iç bağlantısı varsa kaldırın (varsayılan olarak kapalıdır). |
| [`/Zc:noexceptTypes`](zc-noexcepttypes.md) | C++ 17 **`noexcept`** kurallarını (varsayılan olarak c++ 17 veya üzeri) uygulayın. |
| [`/Zc:preprocessor`](zc-preprocessor.md) | Yeni uygun Önişlemci 'yi kullanın (C11/C17 dışında varsayılan olarak kapalıdır). |
| [`/Zc:referenceBinding`](zc-referencebinding-enforce-reference-binding-rules.md) | Bir UDT geçici değeri, const olmayan bir lvalue başvurusuna bağlanamaz (varsayılan olarak kapalıdır). |
| [`/Zc:rvalueCast`](zc-rvaluecast-enforce-type-conversion-rules.md) | Standart C++ açık tür dönüştürme kurallarını zorla (varsayılan olarak kapalıdır). |
| [`/Zc:sizedDealloc`](zc-sizeddealloc-enable-global-sized-dealloc-functions.md) | C++ 14 genel boyutlu ayırmayı kaldırma işlevlerini etkinleştirin (varsayılan olarak açık). |
| [`/Zc:strictStrings`](zc-strictstrings-disable-string-literal-type-conversion.md) | Dize sabit değerini veya dönüştürmeyi devre dışı bırak `char*` `wchar_t*` (varsayılan olarak kapalı). |
| [`/Zc:ternary`](zc-ternary.md) | İşlenen türlerinde koşullu işleç kuralları zorlayın (varsayılan olarak kapalıdır). |
| [`/Zc:threadSafeInit`](zc-threadsafeinit-thread-safe-local-static-initialization.md) | İş parçacığı güvenli yerel statik başlatmayı etkinleştirin (varsayılan olarak açık). |
| [`/Zc:throwingNew`](zc-throwingnew-assume-operator-new-throws.md) | Hata durumunda olduğunu varsayar **`operator new`** (varsayılan olarak kapalıdır). |
| [`/Zc:trigraphs`](zc-trigraphs-trigraphs-substitution.md) | Trigraf 'yi etkinleştirin (varsayılan olarak kapalı, devre dışı). |
| [`/Zc:twoPhase`](zc-twophase.md) | Uyumsuz şablon ayrıştırma davranışını kullanın (varsayılan olarak uyumlu). |
| [`/Zc:wchar_t`](zc-wchar-t-wchar-t-is-native-type.md) | **`wchar_t`** , bir typedef değil, yerel bir türdür (varsayılan olarak açık). |

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
