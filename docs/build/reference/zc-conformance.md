---
title: /ZC (Uyumluluk) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zc
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8b87774b9c011d6ea5ab92d3c1b44e4af2b6091
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zc-conformance"></a>/Zc (Uyumluluk)

Kullanabileceğiniz **/Zc** derleyici seçenekleri standart ya da Microsoft'a özgü derleyici davranışı belirtin.

## <a name="syntax"></a>Sözdizimi

> **/ Zc:**_seçeneği_{,_seçeneği_}

## <a name="remarks"></a>Açıklamalar

Visual Studio C veya C++ standart ile uyumlu olmayan bir uzantı uyguladığında kullanabileceğiniz bir `/Zc` standart uyumsuz veya Microsoft'a özgü davranışını belirtmek için Uyumluluk seçeneği. İçin bazı seçenekler, büyük ölçekli önemli değişiklikler için var olan kodu önlemek için varsayılan olarak Microsoft'a özgü davranıştır. Diğer durumlarda, standart davranış burada önemli değişiklikler maliyetlerini geliştirmeleri güvenlik, performans veya uyumluluk gereksinimlerine ağır bastığı varsayılandır. Varsayılan ayar, her uyumluluk seçeneğinin Visual Studio'nun daha yeni sürümlerinde değişebilir. Her uyumluluk seçenek hakkında daha fazla bilgi için belirli seçeneği için konusuna bakın. [/ İzin veren-](permissive-standards-conformance.md) derleyici seçeneği kendi uyumluluğunu ayarı varsayılan olarak ayarlı değil Uyumluluk seçenekleri örtük olarak ayarlar.

Bunlar `/Zc` derleyici seçenekleri:

|Seçenek|Davranış|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C ++ 17 aşırı hizalanmış dinamik ayırma etkinleştir (C ++ 17 varsayılan değer olarak).|
|[Otomatik\[-\]](zc-auto-deduce-variable-type.md)|Yeni standart C++ anlamı için zorunlu `auto` (üzerinde varsayılan olarak).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|Dış bağlantı için etkinleştirme `constexpr` değişkenleri (varsayılan olarak kapalıdır).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|Standart C++ zorunlu `for` kuralları kapsamı (üzerinde varsayılan olarak).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|Örtük etkinleştir `noexcept` gerekli işlevlerde (üzerinde varsayılan olarak).|
|[Satır içi\[-\]](zc-inline-remove-unreferenced-comdat.md)|Comdat'ı ise veya yalnızca iç bağlantı varsa başvurulmayan işlevi veya verileri kaldırma (varsayılan olarak kapalıdır).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C ++ 17 noexcept kurallarını zorlama (üzerinde varsayılan C ++ 17 veya üzeri).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|UDT geçici bir const olmayan lvalue başvuru bağlanamaz (varsayılan olarak kapalıdır).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|Standart C++ açık tür dönüştürme kurallarını zorlama (varsayılan olarak kapalıdır).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C ++ 14 küresel ölçekli ayırmayı kaldırma işlevleri etkinleştir (üzerinde varsayılan olarak).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|Devre dışı bırak sabit değer dizesi için `char*` veya `wchar_t*` dönüştürme (varsayılan olarak kapalıdır).|
|[Üçlü\[-\]](zc-ternary.md)|İşlenen türleri koşullu işleç kurallarında zorlamak (varsayılan olarak kapalıdır).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|İş parçacığı yerel statik başlatma etkinleştir (üzerinde varsayılan olarak).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|Varsayın `operator new` hatada oluşturur (varsayılan olarak kapalıdır).|
|[trigrafları\[-\]](zc-trigraphs-trigraphs-substitution.md)|Trigrafları (varsayılan olarak geçersiz, kapalı) etkinleştirin.|
|[twoPhase-](zc-twophase.md)|Ayrıştırma (varsayılan olarak uyumsuz) davranışını uyumsuz şablonunu kullanın.|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` yerel bir tür, bir typedef (üzerinde varsayılan olarak).|

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](setting-compiler-options.md)
