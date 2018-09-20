---
title: Derleyici iç bilgileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a11efde9be7e990608277a242d7018f347df0ce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383245"
---
# <a name="compiler-intrinsics"></a>Derleyici İç Bilgileri

Çoğu işlev kitaplıklarda yer alır, ancak bazı işlevler yerleşik olarak bulunan (diğer bir deyişle, iç) derleyici. Bunlar, iç işlevler veya iç öğeler olarak adlandırılır.

## <a name="remarks"></a>Açıklamalar

Bir işlev iç öğeyse, söz konusu işlevin kodu bir işlev çağrısının yükünden ve bu işlev için derleyicisindeki üst düzeyde verimli olan makine yönergelerine izin genelde satır içine eklenir, ' dir. Bazı iyileştirmeler kullanılabilir hale şekilde iyileştirici kaç adet iç öğenin davranış, yerleşik bir bilgiye sahip olduğundan bir iç öğe genellikle eşdeğer satır içi derlemeden daha hızlıdır kullanılamayan satır içi derlemenin kullanılması sırasında. Ayrıca iyileştirici yapı içini farklı şekilde genişletebilir, arabellekleri farklı hizalayabilir veya çağrının bağımsız değişkenler ve bağlam bağlı olarak diğer ayarlamaları yapın.

Visual C++'da kullanılabilen yapı içleri bazı hedef mimariler için kullanılabilir bazı iç öğeler kullanılabilir değil ve kodun diğer derleyicilerle derlenmesi durumunda kullanılamayabilir çünkü kullanımı, kodun taşınabilirliğini etkiler. Tüm mimariler için. Ancak, yapı içleri genelde satır içi derlemeden daha fazla taşınabilir değildir. Satır içi derlemenin desteklenmediği 64-bit mimarilerde iç yapılar gereklidir.

Bazı iç öğeler gibi `__assume` ve `__ReadWriteBarrier`, iyileştiricinin davranışını etkileyen derleyiciye bilgi sağlar.

Bazı iç öğeler yalnızca iç öğe olarak kullanılabilir ve bazıları hem işlev ve iç uygulamalarda kullanılabilir. Tüm iç özellikleri etkinleştirme istediğiniz veya derleyicinin yalnızca belirli işlevleri etkinleştirme istediğinize bağlı olarak iki yoldan biriyle iç öğe uygulaması kullanmasını söyleyebilirsiniz. İlk yol kullanmaktır `#pragma intrinsic(` *iç işlevi-adı-liste*`)`. Pragma, tek bir iç yapıyı veya virgüllerle ayrılmış birden çok iç yapıyı belirtmek için kullanılabilir. İkinci kullanmaktır [(iç işlevler Oluştur) /Oi](../build/reference/oi-generate-intrinsic-functions.md) derleyici seçeneği, belirli bir platformda tüm yapı içleri kullanılabilir hale getirir. Altında **/Oi**, kullanın `#pragma function(` *iç işlevi-adı-liste* `)` bir işlev çağrısı bir iç öğe yerine kullanılacak zorlamak için. Belirli bir iç belgelerine, notlar, yordam yalnızca bir iç öğe olarak kullanılabilir ve ardından olup olmamasına bakılmaksızın iç öğe uygulaması kullanılır **/Oi** veya `#pragma intrinsic` belirtilir. Tüm durumlarda **/Oi** veya `#pragma intrinsic` sağlar, ancak zorlamaz iyileştirici kullanmak üzere. İyileştirici hala işlevi çağırabilir.

Bazı standart C/C++ Kitaplığı işlevleri bazı mimarilerde iç uygulamalar kullanılabilir. Bir CRT işlevini çağırırken, iç öğe uygulaması kullanılır **/Oi** komut satırında belirtilir.

Bir üstbilgi dosyası \<intrin.h >, olan ortak işlevlere yönelik prototipleri bildiren kullanılabilir. Üreticiye özgü yapı içleri kullanılabilir \<immintrin.h > ve \<ammintrin.h > üst bilgi dosyaları. Ayrıca, belirli Windows üstbilgileri derleyici içine eşleyen işlevleri bildirir.

Aşağıdaki bölümlerde, çeşitli mimarilerde bulunan tüm yapı içleri listelenir. Yapı içlerini belirli hedef işlemci üzerinde nasıl çalıştığı hakkında daha fazla bilgi için üretici firmanın referans belgelerine bakın.

- [ARM İç Bilgileri](../intrinsics/arm-intrinsics.md)

- [x86 İç Bilgi Listesi](../intrinsics/x86-intrinsics-list.md)

- [x64 (amd64) İç Bilgi Listesi](../intrinsics/x64-amd64-intrinsics-list.md)

- [Tüm Mimarilerde Kullanılabilen İç Bilgiler](../intrinsics/intrinsics-available-on-all-architectures.md)

- [İç İşlevlerin Alfabetik Listesi](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)

## <a name="see-also"></a>Ayrıca Bkz.

[ARM Assembler Başvurusu](../assembler/arm/arm-assembler-reference.md)<br/>
[Microsoft Macro Assembler Başvurusu](../assembler/masm/microsoft-macro-assembler-reference.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[C Çalışma Zamanı Kitaplığı Başvurusu](../c-runtime-library/c-run-time-library-reference.md)