---
title: Derleyici iç bilgileri
ms.date: 09/02/2019
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
ms.openlocfilehash: 6f41b56995e1a5a7d7f4267cb1def5370f953d5c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171677"
---
# <a name="compiler-intrinsics"></a>Derleyici iç bilgileri

Çoğu işlev kitaplıklarda bulunur, ancak bazı işlevler derleyiciye (yani, iç) derlenmelidir. Bunlar iç işlevler veya iç bilgiler olarak adlandırılır.

## <a name="remarks"></a>Açıklamalar

Bir işlev içsel ise, bu işlevin kodu genellikle satır içi olarak eklenir, bir işlev çağrısının ek yükünü ortadan kaldırır ve bu işlev için yüksek düzeyde verimli makine yönergelerine izin verir. En iyi duruma getirme, en çok sayıda iç yapı ile ilgili yerleşik bir bilgiye sahip olduğundan ve satır içi derleme kullanıldığında kullanılamayan bazı iyileştirmeler kullanılabilir olduğundan, bir iç öğe genellikle denk satır içi derlemeden daha hızlıdır. Ayrıca, iyileştirici iç farklı şekilde genişleyebilir, arabellekleri farklı hizalayabilir veya çağrının bağlamına ve bağımsız değişkenlerine bağlı olarak diğer ayarlamaları yapabilirsiniz.

Kod diğer derleyiciler ile derlenirse ve bazı hedef mimarilerde kullanılabilir olabilecek bazı iç bilgiler C++ tüm mimarilerde kullanılabilir değilse, iç yapı kullanımı kod taşınabilirliği etkiler. Ancak, iç bilgiler genellikle satır içi derlemeden daha taşınabilir. Satır içi derlemenin desteklenmediği 64 bitlik mimarilerde iç bilgiler gereklidir.

`__assume` ve `__ReadWriteBarrier`gibi bazı iç bilgiler derleyiciye bilgi sağlar ve bu da iyileştiricinin davranışını etkiler.

Bazı iç bilgiler yalnızca iç bilgiler olarak kullanılabilir ve bazıları hem işlev hem de iç uygulamalarda kullanılabilir. Yalnızca belirli işlevleri etkinleştirmek mi yoksa tüm iç bilgileri etkinleştirmek mi istediğinize bağlı olarak derleyicinin iç uygulamayı iki şekilde kullanmasını bildirebilirsiniz. İlk yol `#pragma intrinsic(`*iç işlev adı-liste*`)`kullanmaktır. Pragma, virgülle ayrılmış tek bir iç veya birden çok iç yapı belirtmek için kullanılabilir. İkincisi, belirli bir platformdaki tüm iç bilgileri kullanılabilir hale getiren [/Oi (iç Işlevler üret)](../build/reference/oi-generate-intrinsic-functions.md) derleyici seçeneğini kullanmaktır. **/Oi**altında, bir işlev çağrısının bir iç yerine kullanılmasına zorlamak için `#pragma function(`*iç işlev adı-liste*`)` kullanın. Belirli bir iç belge için belgeler yalnızca iç öğe olarak kullanılabilir olduğunda, iç uygulama **/Oi** veya `#pragma intrinsic` belirtildiğinden bağımsız olarak kullanılır. Her durumda, **/Oi** veya `#pragma intrinsic` izin verir, ancak en iyi duruma getirmeyi zorlamaz. İyileştirici hala işlevi çağırabilir.

Bazı standart C/C++ kitaplık işlevleri bazı mimarilerde iç uygulamalarda kullanılabilir. CRT işlevini çağırırken, komut satırında **/Oi** belirtilmişse iç uygulama kullanılır.

\<Intrin. h > bir üst bilgi dosyası, ortak iç işlevler için prototipler bildiren kullanılabilir. Üreticiye özgü iç bilgiler \<ımmintrin. h > ve \<ammintrin. h > üst bilgi dosyalarında mevcuttur. Ayrıca, bazı Windows üstbilgileri bir derleyici iç üzerine eşlenen işlevleri bildirir.

Aşağıdaki bölümlerde, çeşitli mimarilerde bulunan tüm iç bilgiler listelenmektedir. İç bilgilerin belirli bir hedef işlemcide nasıl çalıştığı hakkında daha fazla bilgi için, üreticinin başvuru belgelerine bakın.

- [ARM iç bilgileri](../intrinsics/arm-intrinsics.md)

- [ARM64 içleri](../intrinsics/arm64-intrinsics.md)

- [x86 iç bilgi listesi](../intrinsics/x86-intrinsics-list.md)

- [x64 (amd64) İç Bilgi Listesi](../intrinsics/x64-amd64-intrinsics-list.md)

- [Tüm mimarilerde kullanılabilir iç bilgiler](../intrinsics/intrinsics-available-on-all-architectures.md)

- [İç işlevlerin alfabetik listesi](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler başvurusu](../assembler/arm/arm-assembler-reference.md)<br/>
[Microsoft Macro Assembler başvurusu](../assembler/masm/microsoft-macro-assembler-reference.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md)
