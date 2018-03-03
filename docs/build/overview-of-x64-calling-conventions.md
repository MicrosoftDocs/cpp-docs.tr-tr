---
title: "X64 genel bakış çağırma kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac42eb934692fb9eaecf345b75e7544e7078f07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-x64-calling-conventions"></a>x64 Çağırma Kurallarına Genel Bakış
X86 iki önemli farklılıkları ve [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 64-bit adresleme yeteneği olan ve düz 16 64-bit birtakım genel kullanım için kaydeder. Genişletilmiş kayıt kümesi [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] kullanan [__fastcall](../cpp/fastcall.md) çağırma kuralı ve bir RISC tabanlı özel durum işleme modeli. `__fastcall` Kuralı kayıtları ilk dört bağımsız değişkenler ve yığın çerçevesi için ek bağımsız değişkenler geçirmek için kullanılır.  
  
 Aşağıdaki derleyici seçeneği, uygulamanız için en iyi hale getirmenize yardımcı [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]:  
  
-   [/ favor (Mimari özellikleri için iyileştirme)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## <a name="calling-convention"></a>Çağırma kuralı  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] Uygulama ikili arabirimi (ABI) varsayılan olarak dört kayıt hızlı arama çağırma kuralı kullanır. Çağrı yığınındaki bu kayıtları kaydetmek callees için gölge deposu olarak ayrılmış alanı. Bir işlev çağrısı için bağımsız değişkenleri ve bu bağımsız değişkenler için kullanılan kayıtları arasında katı bire yoktur. 8 bayt cinsinden uymayan veya 1, 2, 4 veya 8 bayt olmayan herhangi bir bağımsız değişken başvuruyla geçirilmelidir. Tek bir bağımsız değişken birden çok kayıt arasında yaymaya ilişkin hiçbir girişim yoktur. X87 yazmaç yığını kullanılmayan. Aranan tarafından kullanılıyor olabilir, ancak işlev çağrıları arasında geçici olarak düşünülmelidir. Tüm kayan nokta işlemleri yapılır 16 XMM kayıtları kullanılarak. Tamsayı bağımsız değişkenler yazmaçlar RCX, RDX, R8 ve R9 geçirilir. Kayan nokta değişkenleri XMM0L, XMM1L, XMM2L ve XMM3L geçirilir. 16 bayt bağımsız değişkenleri başvuruya göre geçirilir. Parametre geçirme ayrıntılı olarak açıklanmıştır [parametre geçirme](../build/parameter-passing.md). Bu kayıtları yanı sıra RAX, R10, R11, XMM4 ve XMM5 geçici olarak kabul edilir. Diğer tüm kayıtlar geçici olmayan. YAZMAÇ kullanımı ayrıntılı olarak belgelenmiştir [kullanımını Kaydet](../build/register-usage.md) ve [çağıran ve çağrılan kaydedilmiş kayıtları](../build/caller-callee-saved-registers.md).  
  
 Arayan Aranan parametreleri için alan ayırma sorumludur ve Aranan bu kadar sayıda parametre almaz olsa bile her zaman dört kayıt parametrelerini depolamak için yeterli alan ayırmanız gerekir. Prototipi oluşturulmamış dil C işlevlerini ve vararg C/C++ işlevleri desteği basitleştirir. Vararg veya prototipi oluşturulmamış işlevler için herhangi bir kayan nokta değerlerini gereken yinelenen karşılık gelen genel amaçlı kayıttaki. İlk dört ötesinde herhangi bir parametre, gölge mağazada çağrısı önce ilk dört yukarıda yığında depolanmalıdır. Vararg işlev ayrıntıları bulunabilir [Varargs](../build/varargs.md). Prototipi oluşturulmamış işlev bilgisi ayrıntılı olarak [prototipi oluşturulmamış işlevler](../build/unprototyped-functions.md).  
  
## <a name="alignment"></a>Hizalama  
 Çoğu yapıları kendi doğal hizalama hizalanır. Yığın işaretçisi birincil istisnaları ve `malloc` veya `alloca` performansa yardımcı olmak için 16 bayt hizalı bellek. 16 bayt üzerindeki hizalama el ile yapmanız gerekir, ancak 16 bayt XMM işlemleri için ortak bir hizalama boyutu olduğundan, bu çoğu kod için çalışması gerekir. Yapı düzeni ve hizalama hakkında daha fazla bilgi için bkz: [türler ve depolama](../build/types-and-storage.md). Yığın düzeni hakkında daha fazla bilgi için bkz: [yığın kullanımı](../build/stack-usage.md).  
  
## <a name="unwindability"></a>Unwindability  
 Geçici olmayan Yazmaçları değiştirmeyin işlevleri yaprak işlevlerdir. Yaprak olmayan işlevi geçici olmayan RSP, örneğin, bir işlevi çağırmak ya da yerel değişkenler için ek yığın alanı ayırma değişebilir. Bir özel durum işlendiğinde geçici olmayan Yazmaçları kurtulmak için yaprak olmayan işlevleri düzgün rasgele bir yönerge konumundaki işlev bırakma açıklar statik verileri ile Açıklama eklenmelidir. Bu veri olarak depolanması *pdata*, veya sırayla başvurduğu yordamı veri *xdata*, özel durum verileri işleme. Xdata unwinding bilgiler içerir ve ek pdata veya bir özel durum işleyici işlevi işaret edebilir. Xdata içinde açıklanan düzgün olabilmesi açıklanabilmeleri ve sonuç ileri derecede kısıtlı. Yığın işaretçisi yaprak işlevlerinde dışında bir bitiş veya giriş, parçası olmayan kod herhangi bir bölgede 16 bayt hizalı gerekir. Yaprak işlevleri pdata ve xdata gerekli değildir için yalnızca bir dönüş taklit ederek sapmasına. İşlev açıklanabilmeleri ve sonuç uygun yapısı hakkında daha fazla ayrıntı için bkz: [giriş ve bitiş](../build/prolog-and-epilog.md). Özel durum işleme ve özel durum işleme ve pdata ve xdata geriye doğru izleme hakkında daha fazla bilgi için bkz: [özel durum işleme (x64)](../build/exception-handling-x64.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 Yazılım Kuralları](../build/x64-software-conventions.md)