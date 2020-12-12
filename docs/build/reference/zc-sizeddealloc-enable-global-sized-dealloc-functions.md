---
description: 'Şu konuda daha fazla bilgi edinin:/Zc: Sizeddeallocation (genel boyutlu ayırmayı kaldırma Işlevlerini etkinleştir)'
title: '/Zc: Sizeddeallocation (genel boyutlu ayırmayı kaldırma Işlevlerini etkinleştir)'
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: 4e40355dc3c61f725ca9996dc4c91c0604866fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269074"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc: Sizeddeallocation (genel boyutlu ayırmayı kaldırma Işlevlerini etkinleştir)

**/Zc: Sizeddeallocation** derleyici seçeneği, derleyicinin, `operator delete` `operator delete[]` `size_t` nesne boyutu kullanılabilir olduğunda ikinci bir parametresi olan küresel veya işlevleri tercihe bağlı olarak çağırmasını söyler. Bu işlevler, `size_t` deayırıcı performansını iyileştirmek için parametresini kullanabilir.

## <a name="syntax"></a>Syntax

> **/Zc: Sizeddeayırma**[ **-** ]

## <a name="remarks"></a>Açıklamalar

C++ 11 standardında statik üye işlevlerini tanımlayabilir `operator delete` ve `operator delete[]` ikinci bir `size_t` parametre alabilirsiniz. Genellikle bunlar, nesne için daha etkin ayırıcıları ve anlaşmacıları uygulamak üzere [operatör yeni](../../cpp/new-operator-cpp.md) işlevleriyle birlikte kullanılır. Ancak, C++ 11 genel kapsamda bir dizi ayırmayı kaldırma işlevi tanımlamaz. C++ 11 ' de, ikinci bir parametreye sahip genel ayırmayı kaldırma işlevleri `size_t` yerleştirme silme işlevleri olarak kabul edilir. Bir boyut bağımsız değişkeni geçirerek açıkça çağrılması gerekir.

C++ 14 standart, derleyicinin davranışını değiştirir. Genel tanımladığınızda `operator delete` ve `operator delete[]` türünde ikinci bir parametre alan `size_t` , derleyici üye kapsam sürümleri çağrılmıyorsa ve nesnenin boyutu kullanılabilir olduğunda bu işlevleri çağırmayı tercih eder. Derleyici, boyut bağımsız değişkenini örtük olarak geçirir. Tek bağımsız değişken sürümleri, derleyici serbest bırakılmış nesnenin boyutunu belirleyene zaman çağrılır. Aksi takdirde, çağırma işlevinin çağırmak için bir sürümü seçmeye yönelik olağan kurallar, hala geçerlidir. Genel işlevlere yapılan çağrılar, kapsam çözümleme işleci ( `::` ) tarafından ayırmayı kaldırma işlev çağrısına önceden bekleniyor ile açıkça belirtilebilir.

Varsayılan olarak, Visual Studio 2015 ' den itibaren Visual C++, bu C++ 14 standart davranışını uygular. Bunu, **/Zc: Sizeddeayırma** derleyici seçeneğini ayarlayarak açıkça belirtebilirsiniz. Bu, olası bir değişikliği temsil eder. Eski davranışı korumak için **/Zc: Sizeddeallocation-** seçeneğini kullanın, örneğin, kodunuzun yerleştirme silme işleçlerini ikinci bir parametre türünde kullanır `size_t` . Tek parametre sürümlerini çağır türünde ikinci parametreye sahip olan genel ayırmayı kaldırma işlevlerinin varsayılan Visual Studio kitaplığı uygulamaları `size_t` . Kodunuz yalnızca tek parametreli genel işleç Delete ve operator delete [] sağlarsa, genel boyutlu ayırmayı kaldırma işlevlerinin varsayılan kitaplık uygulamaları genel işlevlerinizi çağırır.

**/Zc: Sizeddeayırma** derleyicisi seçeneği varsayılan olarak açık. [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: sizeddeayırmayı** etkilemez.

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Konfigürasyonlar** açılan menüsünde **Tüm Konfigürasyonlar**' ı seçin.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: Sizeddeallocation** veya **/Zc: sizeddeallocation** ' i içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
