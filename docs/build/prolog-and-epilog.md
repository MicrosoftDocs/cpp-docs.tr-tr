---
title: "Giriş ve bitiş | Microsoft Docs"
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
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 700b467065d17a61dcfabf9dcaa6577a7ecffc11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="prolog-and-epilog"></a>Giriş ve Bitiş
Yığın alanı ayıran her işlev, diğer işlevleri, kalıcı Yazmaçları kaydeden veya özel durum işleme kullanan çağrıları adres sınırları ilgili işlev tablosu girişi ile ilişkilendirilmiş bırakma verileriyle açıklanmıştır bir giriş olması gerekir ( bakın[Özel durum işleme (x64)](../build/exception-handling-x64.md)). Giriş bağımsız değişkeni ev adresleri Yazmaçları gerekirse iter kalıcı Yazmaçları yığında kaydeder, Yereller ve temporaries için yığın sabit parçası ayırır ve isteğe bağlı olarak bir çerçeve işaretçisi oluşturur. İlişkili veri bırakma giriş eylemi açıklayan gerekir ve giriş kodu etkisini geri almak gerekli bilgileri sağlamanız gerekir.  
  
 Yığındaki sabit ayırma birden fazla sayfa olup olmadığını (diğer bir deyişle, 4096 bayt büyük), yığın ayırma birden fazla sanal bellek sayfasını kapsayabilir ve gerçekte ayrılan önce ayırma bu nedenle, denetlenmelidir mümkündür. Girişten çağrılabilen ve hangi bağımsız kayıtların hiçbirini silmiyor özel bir yordama bu amaç için sağlanır.  
  
 Kalıcı Yazmaçları kaydetmek için tercih edilen yöntem bunları sabit yığın ayırma önce yığına taşımaktır. Kalıcı yazmaçlar kaydedilmeden önce büyük olasılıkla bir 32 bit öteleme adresine gerekli olacak sonra sabit yığın ayırma gerçekleştirilen, kaydedilen (bağlarsanız, yazmaçların gönderimleri yalnızca hareket ettikçe kadar hızlı ve dolayısıyla kalması gereken alanı kaydetmek yakın gelecekte gönderimleri arasında örtük bağımlılık rağmen). Kalıcı Yazmaçları herhangi bir sırada kaydedilebilir. Ancak, giriş kalıcı bir kayıttaki ilk kez kullanıyorsanız kaydetmeyi olması gerekir.  
  
 Tipik bir giriş için kod olabilir:  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
sub      RSP, fixed-allocation-size  
lea      R13, 128[RSP]  
...  
```  
  
 Bu giriş RCX bağımsız değişken kaydını kendi konumunda depolar, kaydeder kalıcı R13-R15 kayıtlarını kaydeder, yığın çerçevesi sabit parçası ayırır ve 128 bayt sabit ayırma alanına işaret eden bir çerçeve işaretçisi oluşturur. Bir uzaklık kullanarak bir baytlık sapmalarla ele alınması gereken sabit ayırma alanının daha fazla bilgi sağlar.  
  
 Sabit ayırma boyutu belleğin bir sayfası eşit veya daha büyük ise, bir yardımcı işlevini RSP değiştirmeden önce çağrılmalıdır. Bu yardımcı, __chkstk, yığının düzgün şekilde genişletildiğinden emin olmak için to-tahsis edilecek yığın aralığın yoklama için sorumludur. Bu durumda, önceki giriş örneği yerine olacaktır:  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
mov      RAX,  fixed-allocation-size  
call   __chkstk  
sub      RSP, RAX  
lea      R13, 128[RSP]  
...  
```  
  
 __Chkstk Yardımcısı R10, R11 ve koşul kodları dışındaki tüm kayıtları değiştirmez. Özellikle, onu değişmeden RAX dönün ve tüm kalıcı Yazmaçları ve bağımsız değişken geçirme kayıtları değiştirilmemiş şekilde bırakmak.  
  
 Her bir işlev çıkış bitiş kodu var. Normal olarak yalnızca bir giriş gelirken, çok sayıda sonuç olabilir. Bitiş kodu sabit ayırma boyutunu yığına (gerekirse) kırpar sabit yığın ayırmayı kaldırır, kayıtlı değerlerini yığından pencerelerinin tarafından kalıcı Yazmaçları geri yükler ve döndürür.  
  
 Bitiş kodu katı bir dizi kuralla bırakma kodu için güvenilir bir şekilde bırakma özel durumlar ve kesmelerin aracılığıyla izlemeniz gerekir. Bu miktarını azaltır her bitiş açıklamak için hiçbir ek veriler gerektiğinden gerekli veri bırakma. Bunun yerine, bırakma kodunun bir bitiş bir bitiş tanımlamak için bir kod akışını ileri tarayarak yürütülmekte olan belirleyebilirsiniz.  
  
 Çerçeve işaretçisi kullanılıyorsa yığın sabit parçası ilk işlevi sonra bitiş ayırması gerekir, kalıcı Yazmaçları Sil'i ve denetim çağıran işleve döndürülür. Örneğin,  
  
```  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Çerçeve işaretçisi işlevinde kullanılırsa, ardından yığın bitiş yürütülmeden önce sabit, ayırma için kırpılmış olması gerekir. Bu teknik olarak değil, bitiş parçasıdır. Örneğin, aşağıdaki bitiş önceden kullanılmış olan girişi geri almak için kullanılabilir:  
  
```  
lea      RSP, -128[R13]  
; epilogue proper starts here  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Uygulamada, çerçeve işaretçisi kullanıldığında, aşağıdaki bitiş yerine kullanılacak şekilde RSP iki adımda ayarlamak için iyi bir neden yoktur:  
  
```  
lea      RSP, fixed-allocation-size - 128[R13]  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Bunlar yalnızca hukuk formlar bir bitiş için aynıdır. Aşağıdakilerden birini oluşmalıdır bir `add RSP,constant` veya `lea RSP,constant[FPReg]`, ardından sıfır veya daha fazla 8 baytlık kayıt POP ve dönüş veya bir jmp bir dizi. (Yalnızca bir alt jmp deyimlerinin bitiş izin verilebilir. Bunlar yalnızca ModRM bellek başvurularıyla jmps sınıfına burada ModRM mod alanı değerinin 00 değildir. Bitiş ModRM mod alan değeri 01 veya 10 ile jmps kullanımı yasaktır. Bkz. Tablo A-15 AMD x86 64 mimarisi Programcı el ile birim 3'te: genel amaçlı ve izin verilen ModRM başvuruları hakkında daha fazla bilgi için sistem yönergeleri.). Başka bir kod yer alabilir. Özellikle, hiçbir şey dönüş değeri yüklenmesini de dahil olmak üzere bir bitiş içinde zamanlanabilir.  
  
 Çerçeve işaretçisi kullanılmadığı zaman bitiş kullanması gerektiğini, Not `add RSP,constant` yığınının sabit bölümü kaldırılamıyor. Değil kullanabilir `lea RSP,constant[RSP]` yerine. Sonuç için arama yaparken tanımak için daha az desen bırakma kodunun olması için bu kısıtlama yok.  
  
 Bu kurallara bir bitiş şu anda yürütülmekte olan belirlemek ve arama işlevini bağlamı yeniden izin vermek için bitiş kalanı yürütülmesi benzetimini yapmak için bırakma kodu sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x64 Yazılım Kuralları](../build/x64-software-conventions.md)