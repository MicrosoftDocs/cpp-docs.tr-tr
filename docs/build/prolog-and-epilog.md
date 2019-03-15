---
title: x64 giriş ve bitiş
ms.date: 12/17/2018
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
ms.openlocfilehash: a225786853fcc2eb7b6a21de29f1ccf4901e4377
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809996"
---
# <a name="x64-prolog-and-epilog"></a>x64 giriş ve bitiş

Yığın alanı ayırır her işlev, ilgili işlevi tablosu girişiyle ilişkili geriye doğru izlenen veri adres sınırları açıklanan bir giriş diğer işlevleri, kalıcı Yazmaçları kaydeder veya özel durum işleme kullanan bir çağrı olması gerekir. Daha fazla bilgi için [x64 özel durum işleme](../build/exception-handling-x64.md). Giriş bağımsız değişkeni kayıtlara ev adresleri gerekirse kalıcı Yazmaçları yığına, Yereller ve değerlendirmesidir için sabit bir yığın parçası ayırır ve isteğe bağlı olarak bir çerçeve işaretçisi oluşturur kaydeder. İlişkili veri bırakma, giriş eylemi açıklamak gerekir ve giriş kodu etkisini geri almak gereken bilgileri sağlamanız gerekir.

Sabit ayırma yığınında birden fazla sayfa olup olmadığını (diğer bir deyişle, 4096 bayt daha büyük), birden fazla sanal bellek sayfa yığın ayırma kapsayabilir ve ayırma, kendisine ayrılan önce bu nedenle, işaretlenmelidir mümkündür. Girişten çağrılabilen ve herhangi bir bağımsız değişken kayıtları yok değil, özel bir yordama bu amaç için sağlanır.

Yığına sabit yığın ayırma önce bunları taşımak için kalıcı kayıtları kaydetmek için tercih edilen yöntem var. Kalıcı kayıtlar kaydedilmeden önce sabit yığın ayırma gerçekleştirilirse, ardından en büyük olasılıkla bir 32-bit öteleme kaydedilmiş kayıt alanı ele almak için gereklidir. (Bağlarsanız, bildirim yazmaçların taşır ve bunu beraber göndermeler arasında örtük bağımlılık artma kalmalıdır kadar hızlı ilerleyebilirler.) Kalıcı kayıtlar herhangi bir sırada kaydedilebilir. Ancak, bir kayıt giriş sayfasında ilk kez kullanıyorsanız, kaydetmeyi olması gerekir.

## <a name="prolog-code"></a>Giriş kodu

Tipik bir giriş için kod aşağıdaki gibi olabilir:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    sub    RSP, fixed-allocation-size
    lea    R13, 128[RSP]
    ...
```

Bu giriş bağımsız değişkeni kayıt RCX kendi konumunda depolar, kaydeder kalıcı R13 R15 kayıtlarını kaydeder, sabit bir yığın çerçevesini parçası ayırır ve 128 bayt sabit ayırma alanına işaret eden bir çerçeve işaretçisi oluşturur. Bir uzaklık kullanarak tek baytlık sapmalarla ele alınması için sabit bir tahsisat alanının daha fazla bilgi sağlar.

Sabit ayırma boyutu büyüktür veya eşittir belleğin bir sayfası, bir yardımcı işlev RSP değiştirmeden önce çağrılmalıdır. Bu yardımcı, `__chkstk`, yığının düzgün şekilde genişletildiğinden emin olmak için How-to-tahsis edilecek yığın aralığı araştırmaları. Bu durumda, önceki giriş örneği yerine olacaktır:

```MASM
    mov    [RSP + 8], RCX
    push   R15
    push   R14
    push   R13
    mov    RAX,  fixed-allocation-size
    call   __chkstk
    sub    RSP, RAX
    lea    R13, 128[RSP]
    ...
```

`__chkstk` Yardımcı R10 R11 ve durum kodları dışındaki tüm kayıtları değişiklik yapılmaz. Özellikle, bu RAX'daki değiştirmeden döndürür ve tüm kalıcı yazmaçlar ve bağımsız değişken geçirme kayıtlar üzerinde değişiklik yapılmadan bırakın.

## <a name="epilog-code"></a>Sonuç kodu

Her bir işleve çıkış sonuç kodu bulunmaktadır. Normalde yalnızca bir giriş gelirken, çok sayıda sonuç olabilir. Sonuç kodu (gerekirse) yığını sabit ayırma boyutuna kırpar sabit yığın ayırma kaldırır yığından kaydedilmiş değerleri pencerelerinin tarafından kalıcı kayıtlar geri yükler ve döndürür.

Sonuç kodu katı birtakım kurallara geriye doğru izleme kodu için güvenilir bir şekilde özel durumları ve kesme aracılığıyla geriye doğru izleme izlemeniz gerekir. Bu kurallar miktarını azaltmak her bitiş tanımlamak için ek veri yok gerektiğinden, gerekli veri bırakma. Bunun yerine, geriye doğru izleme kodu bir sonuç ileri bir bitiş tanımlamak için bir kod akışını tarayarak yürütüldüğü belirleyebilirsiniz.

Hiçbir çerçeve işaretçisini kullanılırsa işlevi ve ardından sonuç ilk sabit yığınının parçası ayırması gerekir, kalıcı Yazmaçları POP ve denetim çağırma işlevine döndürülür. Örneğin,

```MASM
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

Çerçeve işaretçisini işlevinde kullanılıyorsa, sonra yığına bitiş yürütülmeden önce sabit ayırma için kırpılmış olması gerekir. Bu eylem teknik olarak değil, sonuç parçasıdır. Örneğin, aşağıdaki sonuç önceden kullanılan giriş geri almak için kullanılabilir:

```MASM
    lea      RSP, -128[R13]
    ; epilogue proper starts here
    add      RSP, fixed-allocation-size
    pop      R13
    pop      R14
    pop      R15
    ret
```

Uygulamada, bir çerçeve işaretçisini kullanıldığında, aşağıdaki bitiş yerine kullanılacak şekilde iki adımda RSP ayarlamak için iyi bir neden yoktur:

```MASM
    lea      RSP, fixed-allocation-size - 128[R13]
    pop      R13
    pop      R14
    pop      R15
    ret
```

Bu form için bir sonuç yalnızca yasal olanlardır. Aşağıdakilerden birini oluşmalıdır bir `add RSP,constant` veya `lea RSP,constant[FPReg]`ve ardından sıfır veya daha fazla 8 baytlık kayıt POP bir dizi ve bir `return` veya `jmp`. (Yalnızca bir alt kümesini `jmp` deyimleri bölümünde izin verilebilir. Özel olarak sınıfının alt kümesidir `jmp` deyimleri ModRM bellek başvurularıyla ModRM mod alan değeri, 00 olduğu. Kullanımını `jmp` mod alan değeri 01 ya da 10 kullanılamaz ModRM ile Bitiş deyimlerinde. Tablo A-15 AMD x86 64 mimari Programcı el ile toplu 3 bakın: Genel amaçlı ve izin verilen ModRM başvuruları hakkında daha fazla bilgi için sistem yönergeleri.) Başka bir kod görünebilir. Özellikle, hiçbir şey bir dönüş değeri yüklenmesini içeren bir sonuç içinde zamanlanabilir.

Çerçeve işaretçisini kullanıldığında, sonuç kullanmalısınız `add RSP,constant` yığınının sabit parçası serbest bırakmak. Değil kullanabilir `lea RSP,constant[RSP]` yerine. Geriye doğru izleme kodu başlangıçları ararken tanımak için daha az desen olması için bu kısıtlama yok.

Bu kurallara bir sonuç şu anda yürütülmekte olan belirler ve çağıran işlevin bağlamı yeniden izin vermek için sonuç geri kalanında yürütülmesini benzetimini yapmak için geriye doğru izleme kodu sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[x64 Yazılım Kuralları](x64-software-conventions.md)
