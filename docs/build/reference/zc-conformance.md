---
title: /Zc (Uyumluluk)
ms.date: 03/06/2018
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 4422524deab2a749c96d5e967bc3223d0c9c9873
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438661"
---
# <a name="zc-conformance"></a>/Zc (Uyumluluk)

**/ZC** derleyici seçeneklerini standart veya Microsoft 'a özgü derleyici davranışını belirtmek için kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

> **/Zc:** _seçenek_{,_seçenek_}

## <a name="remarks"></a>Açıklamalar

Visual Studio, C 'ye bir uzantı uygulamışsa veya C++ standart ile uyumlu olmayan bir `/Zc` uygunluk seçeneği kullanarak standart uyumlu veya Microsoft 'a özgü davranışları belirtebilirsiniz. Bazı seçenekler için, Microsoft 'a özgü davranış, var olan koddaki büyük ölçekli önemli değişikliklere engel olmak için varsayılandır. Diğer durumlarda, varsayılan olarak, güvenlik, performans veya uyumlulukta iyileştirmeler, önemli olmayan değişikliklerin maliyetlerine aykırı olan standart davranıştır. Her uygunluk seçeneğinin varsayılan ayarı, Visual Studio 'nun daha yeni sürümlerinde değişebilir. Her uygunluk seçeneği hakkında daha fazla bilgi için, ilgili seçeneğe yönelik konuya bakın. [/Permissive-](permissive-standards-conformance.md) derleyici seçeneği, varsayılan olarak ayarlı olmayan uygunluk seçeneklerini uyumlu ayarlarına örtülü olarak ayarlar.

Bunlar `/Zc` derleyici seçenekleridir:

|Seçenek|Davranış|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C++ 17 üzerinde hizalanmış dinamik ayırmayı etkinleştirin (varsayılan olarak, C++ 17 ' de).|
|[Otomatik\[-\]](zc-auto-deduce-variable-type.md)|`auto` için yeni standart C++ anlamı zorla (varsayılan olarak açık).|
|[__cplusplus\[-\]](zc-cplusplus.md)|Desteklenen standardı raporlamak için **__cplusplus** makrosunu etkinleştirin (varsayılan olarak kapalı).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|`constexpr` değişkenleri için dış bağlantıyı etkinleştirin (varsayılan olarak kapalı).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Standart C++ `for` kapsam kurallarını zorla (varsayılan olarak açık).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Gerekli işlevlerde örtük `noexcept` etkinleştirin (varsayılan olarak açık).|
|[satır içi\[-\]](zc-inline-remove-unreferenced-comdat.md)|Başvurulmayan işlevi veya verileri COMDAT ise veya yalnızca iç bağlantısı varsa kaldırın (varsayılan olarak kapalıdır).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C++ 17 noexcept kurallarını zorla (C++ 17 veya üzeri sürümlerde varsayılan olarak açık).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Bir UDT geçici değeri, const olmayan bir lvalue başvurusuna bağlanamaz (varsayılan olarak kapalıdır).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|Standart C++ açık tür dönüştürme kurallarını zorla (varsayılan olarak kapalıdır).|
|[Sizeddeayırma\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C++ 14 genel boyutlu ayırmayı kaldırma işlevlerini etkinleştirin (varsayılan olarak açık).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Dize sabit değerini `char*` veya `wchar_t*` dönüşümü devre dışı bırakın (varsayılan olarak kapalı).|
|[Üçlü\[-\]](zc-ternary.md)|İşlenen türlerinde koşullu işleç kuralları zorlayın (varsayılan olarak kapalıdır).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|İş parçacığı güvenli yerel statik başlatmayı etkinleştirin (varsayılan olarak açık).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|`operator new` hata durumunda (varsayılan olarak kapalı) olduğunu varsayın.|
|[trigraf\[-\]](zc-trigraphs-trigraphs-substitution.md)|Trigraf 'yi etkinleştirin (varsayılan olarak kapalı, devre dışı).|
|[twoPhase](zc-twophase.md)|Uyumsuz şablon ayrıştırma davranışını kullanın (varsayılan olarak uyumlu).|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t`, typedef değil, yerel bir türdür (varsayılan olarak açık).|

Visual C++'teki uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
