---
title: Giriş ve bitiş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c2a1a9b1891af1c5616e78932cf4a530a300786
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718880"
---
# <a name="prolog-and-epilog"></a>Giriş ve Bitiş

Yığın alanı ayırır her işlev, adres sınırları ilgili işlevi tablosu girişiyle ilişkili geriye doğru izlenen veri açıklanmıştır bir giriş diğer işlevleri, kalıcı Yazmaçları kaydeder veya özel durum işleme kullanan bir çağrı olmalıdır ( bkz[Özel durum işleme (x64)](../build/exception-handling-x64.md)). Giriş bağımsız değişkeni kayıtlara ev adresleri gerekirse gönderim kalıcı Yazmaçları yığında kaydeder, Yereller ve değerlendirmesidir için sabit bir yığın parçası ayırır ve isteğe bağlı olarak bir çerçeve işaretçisi oluşturur. İlişkili veri bırakma, giriş eylemi açıklamak gerekir ve giriş kodu etkisini geri almak gereken bilgileri sağlamanız gerekir.

Sabit ayırma yığınında birden fazla sayfa olup olmadığını (diğer bir deyişle, 4096 bayt daha büyük), birden fazla sanal bellek sayfa yığın ayırma kapsayabilir ve ayırma, aslında ayrılan önce bu nedenle, işaretlenmelidir mümkündür. Özel bir yordama girişten çağrılabilen ve hangi herhangi bir bağımsız değişken kayıtları yok eder, bu amaç için sağlanır.

Yığına sabit yığın ayırma önce bunları taşımak için kalıcı kayıtları kaydetmek için tercih edilen yöntem var. Kalıcı kayıtlar kaydedilmeden önce büyük ihtimalle 32-bit öteleme adresine gerekli olacak sonra sabit yığın ayırma gerçekleştirilmişse kaydedilen (bağlarsanız, bildirimler kayıtları yalnızca hareket ettikçe kadar hızlı ilerleyebilirler ve dolayısıyla kalmalıdır alanı kaydetmek yakın gelecekte göndermeler arasında örtük bağımlılık artma). Kalıcı kayıtlar herhangi bir sırada kaydedilebilir. Ancak, bir kayıt giriş sayfasında ilk kez kullanıyorsanız, kaydetmeyi olması gerekir.

Tipik bir giriş için kod aşağıdaki gibi olabilir:

```
mov       [RSP + 8], RCX
push   R15
push   R14
push   R13
sub      RSP, fixed-allocation-size
lea      R13, 128[RSP]
...
```

Bu giriş bağımsız değişkeni kayıt RCX kendi konumunda depolar, kaydeder kalıcı R13 R15 kayıtlarını kaydeder, sabit bir yığın çerçevesini parçası ayırır ve 128 bayt sabit ayırma alanına işaret eden bir çerçeve işaretçisi oluşturur. Bir uzaklık kullanarak tek baytlık sapmalarla ele alınması için sabit bir tahsisat alanının daha fazla bilgi sağlar.

Sabit ayırma boyutu büyüktür veya eşittir belleğin bir sayfası, bir yardımcı işlev RSP değiştirmeden önce çağrılmalıdır. Bu yardımcı, __chkstk, yığının düzgün şekilde genişletildiğinden emin olmak için How-to-tahsis edilecek yığın aralığı yoklaması için sorumludur. Bu durumda, önceki giriş örneği yerine olacaktır:

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

__Chkstk Yardımcısı R10 R11 ve durum kodları dışındaki tüm kayıtları değiştirmez. Özellikle, bu RAX'daki değiştirmeden döndürür ve tüm kalıcı yazmaçlar ve bağımsız değişken geçirme kayıtlar üzerinde değişiklik yapılmadan bırakın.

Her bir işleve çıkış sonuç kodu bulunmaktadır. Normalde yalnızca bir giriş gelirken, çok sayıda sonuç olabilir. Sonuç kodu (gerekirse) yığını sabit ayırma boyutuna kırpar sabit yığın ayırma kaldırır yığından kaydedilmiş değerleri pencerelerinin tarafından kalıcı kayıtlar geri yükler ve döndürür.

Sonuç kodu katı birtakım kurallara geriye doğru izleme kodu için güvenilir bir şekilde özel durumları ve kesme aracılığıyla geriye doğru izleme izlemeniz gerekir. Bu azaltır her bitiş tanımlamak için ek veri yok gerektiğinden, gerekli veri bırakma. Bunun yerine, geriye doğru izleme kodu bir sonuç ileri bir bitiş tanımlamak için bir kod akışını tarayarak yürütüldüğü belirleyebilirsiniz.

Hiçbir çerçeve işaretçisini kullanılırsa işlevi ve ardından sonuç ilk sabit yığınının parçası ayırması gerekir, kalıcı Yazmaçları POP ve denetim çağırma işlevine döndürülür. Örneğin,

```
add      RSP, fixed-allocation-size
pop      R13
pop      R14
pop      R15
ret
```

Çerçeve işaretçisini işlevinde kullanılıyorsa, sonra yığına bitiş yürütülmeden önce sabit ayırma için kırpılmış olması gerekir. Bu teknik olarak değil, sonuç parçasıdır. Örneğin, aşağıdaki sonuç önceden kullanılan giriş geri almak için kullanılabilir:

```
lea      RSP, -128[R13]
; epilogue proper starts here
add      RSP, fixed-allocation-size
pop      R13
pop      R14
pop      R15
ret
```

Uygulamada, bir çerçeve işaretçisini kullanıldığında, aşağıdaki bitiş yerine kullanılacak şekilde iki adımda RSP ayarlamak için iyi bir neden yoktur:

```
lea      RSP, fixed-allocation-size - 128[R13]
pop      R13
pop      R14
pop      R15
ret
```

Bu, bir sonuç için tek geçerli biçimler. Aşağıdakilerden birini oluşmalıdır bir `add RSP,constant` veya `lea RSP,constant[FPReg]`ve ardından sıfır veya daha fazla 8 baytlık kayıt POP ve bir dönüş veya bir jmp bir dizi. (Jmp deyimler yalnızca bir alt bölümünde izin verilebilir. Sınıfına ModRM bellek başvurularına tamamıyla jmps burada ModRM mod alanı değerinin 00 şunlardır. Kullanım bitiş ModRM mod alan değeri 01 ya da 10 ile jmps yasaktır. Bkz: Tablo A-15 AMD x86 64 mimari Programcı el ile birim 3'te: genel amaçlı ve izin verilen ModRM başvuruları hakkında daha fazla bilgi için sistem yönergeleri.). Başka bir kod görünebilir. Özellikle, hiçbir şey bir dönüş değeri yüklenmesini içeren bir sonuç içinde zamanlanabilir.

Çerçeve işaretçisini kullanıldığında, sonuç kullanması gerektiğini, Not `add RSP,constant` yığınının sabit parçası serbest bırakmak. Değil kullanabilir `lea RSP,constant[RSP]` yerine. Geriye doğru izleme kodu başlangıçları ararken tanımak için daha az desen olması için bu kısıtlama yok.

Bu kurallara bir sonuç şu anda yürütülmekte olan belirler ve çağıran işlevin bağlamı yeniden izin vermek için sonuç geri kalanında yürütülmesini benzetimini yapmak için geriye doğru izleme kodu sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[x64 Yazılım Kuralları](../build/x64-software-conventions.md)