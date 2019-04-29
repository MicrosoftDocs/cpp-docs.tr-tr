---
title: /Zc (Uyumluluk)
ms.date: 03/06/2018
f1_keywords:
- /zc
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: e24dd53f9c805f57ce974a81a4963434f1868095
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316216"
---
# <a name="zc-conformance"></a>/Zc (Uyumluluk)

Kullanabileceğiniz **/Zc** derleyici seçenekleri, standart veya özel Microsoft derleyici davranışını belirtmek için.

## <a name="syntax"></a>Sözdizimi

> **/ Zc:**_seçeneği_{,_seçeneği_}

## <a name="remarks"></a>Açıklamalar

Visual Studio C veya C++ standardı ile uyumlu olmayan bir uzantı uyguladığında kullanabileceğiniz bir `/Zc` standart öğeyi veya Microsoft'a özgü davranışını belirtmek için Uyumluluğu seçeneği. Bazı seçenekler için mevcut kodu büyük ölçekli bozucu değişiklikleri önlemek için varsayılan olarak Microsoft'a özgü davranışıdır. Diğer durumlarda, standart dışı davranışa burada bozucu değişiklikler maliyetlerini geliştirmeleri güvenlik, performans veya uyumluluk gereksinimlerine ağır bastığı varsayılandır. Varsayılan ayarı her Uyumluluğu seçeneği, Visual Studio'nun daha yeni sürümlerde değişebilir. Her bir uyumluluk seçenek hakkında daha fazla bilgi için belirli seçeneği için konusuna bakın. [/ Permissive-](permissive-standards-conformance.md) derleyici seçeneği, bunların uyumluluğunu ayarı varsayılan olarak ayarlı değil uygunluk seçenekleri örtük olarak ayarlar.

Bunlar `/Zc` derleyici seçenekleri:

|Seçenek|Davranış|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C ++ 17 aşırı hizalanmış dinamik ayırma etkinleştir (C ++ 17 varsayılan değer olarak).|
|[Otomatik\[-\]](zc-auto-deduce-variable-type.md)|İçin yeni standart C++ anlamına zorla `auto` (üzerinde varsayılan olarak).|
|[__cplusplus\[-\]](zc-cplusplus.md)|Etkinleştirme **__cplusplus** desteklenen standart bildirmek için makro (varsayılan olarak kapalıdır).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Etkinleştirmek için dış bağlantısı `constexpr` değişkenler (varsayılan olarak kapalıdır).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Standart C++ zorla `for` kapsama kuralları (üzerinde varsayılan olarak).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Örtük etkinleştir `noexcept` gerekli işlevlerde (üzerinde varsayılan olarak).|
|[Satır içi\[-\]](zc-inline-remove-unreferenced-comdat.md)|COMDAT'ı olan veya yalnızca iç bağlantıya sahipse başvurulmayan işlevi veya verileri kaldır (varsayılan olarak kapalıdır).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C ++ 17 noexcept kurallarını zorla (üzerinde C ++ 17'de veya sonraki sürümlerinde varsayılan olarak).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|Bir UDT geçici bir const olmayan bir lvalue başvurusuna bağlanamaz (varsayılan olarak kapalıdır).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|Standart C++ açık tür dönüşüm kurallarını uygula (varsayılan olarak kapalıdır).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C ++ 14 genel boyutta ayırmayı kaldırma işlevlerini etkinleştir (üzerinde varsayılan olarak).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Devre dışı bırakma dize sabit değerine `char*` veya `wchar_t*` dönüştürme (varsayılan olarak kapalıdır).|
|[Üçlü\[-\]](zc-ternary.md)|İşlenen türlerinde koşullu işleç kurallarını uygula (varsayılan olarak kapalıdır).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|İş parçacığı güvenli yerel statik başlatma etkinleştir (üzerinde varsayılan olarak).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Varsayar `operator new` hatası oluşturur (varsayılan olarak kapalıdır).|
|[Trigrafları\[-\]](zc-trigraphs-trigraphs-substitution.md)|Trigrafları (varsayılan olarak eski kapalı) etkinleştirin.|
|[twoPhase-](zc-twophase.md)|Ayrıştırma davranışının (varsayılan olarak uygun) DSCP şablonu kullanın.|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` Yerel türdür, typedef olduğu (üzerinde varsayılan olarak).|

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
