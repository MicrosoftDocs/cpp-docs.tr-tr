---
title: __fastfail
ms.date: 09/02/2019
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: 34198409c6a57eb494bfe819b367b71405a84e64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222190"
---
# <a name="__fastfail"></a>__fastfail

**Microsoft 'a özgü**

, Çağırma işlemini hemen en düşük yükle sonlandırır.

## <a name="syntax"></a>Sözdizimi

```C
void __fastfail(unsigned int code);
```

### <a name="parameters"></a>Parametreler

*kodudur*\
'ndaki Winnt `FAST_FAIL_<description>` . h veya WDM. h 'den, işlem sonlandırmasının nedenini gösteren bir sembolik sabit.

## <a name="return-value"></a>Dönüş değeri

`__fastfail` İç değer döndürmez.

## <a name="remarks"></a>Açıklamalar

İç `__fastfail` işlem, *hızlı bir başarısızlık* isteğine yönelik bir mekanizma sağlar. Bu işlem, acil bir işlem sonlandırma istemek için bozulmuş olabilecek bir işlemin yoludur. Bozuk program durumu ve kurtarma ötesinde yığın olabilecek kritik hata, normal özel durum işleme olanağı tarafından işlenemiyor. En `__fastfail` az ek yük kullanarak işlemi sonlandırmak için kullanın.

Dahili olarak `__fastfail` , çeşitli mimariye özgü mekanizmalar kullanılarak uygulanır:

|Mimari|Yönergenin|Kod bağımsız değişkeninin konumu|
|------------------|-----------------|-------------------------------|
|x86|Int 0x29|`ecx`|
|X64|Int 0x29|`rcx`|
|ARM|Opcode 0xDEFB|`r0`|
|ARM64|Opcode 0xF003|`x0`|

Hızlı bir başarısızlık isteği kendi içindedir ve genellikle yalnızca iki yönergelerin yürütülmesi gerekir. Hızlı bir başarısızlık isteği yürütüldükten sonra çekirdek, uygun eylemi gerçekleştirir. Kullanıcı modu kodunda, hızlı hata olayı ortaya çıktığında yönerge işaretçisinin ötesinde hiçbir bellek bağımlılığı yoktur. Ciddi bellek bozulması durumunda bile güvenilirliğini en üst düzeye çıkarır.

Winnt. h veya WDM. `FAST_FAIL_<description>` h ' deki sembolik sabitlerden biri olan bağımsızdeğişkeni,hatakoşulununtürünüaçıklar.`code` Hata raporlarına ortama özgü bir biçimde dahil değildir.

Kullanıcı modu hızlı başarısız istekler, 0xC0000409 özel durum kodu ve en az bir özel durum parametresi ile ikinci bir şans sürekliliği olmayan özel durum olarak görünür. İlk istisna parametresi `code` değeridir. Bu özel durum kodu, işlemin bozuk olduğu Windows Hata Bildirimi (WER) ve hata ayıklama altyapısına ve hataya yanıt olarak en düşük işlem içi eylemlerin alınması gerektiğini gösterir. Çekirdek modu hızlı başarısızlık istekleri, `KERNEL_SECURITY_CHECK_FAILURE` adanmış bir hata denetimi kodu (0x139) kullanılarak uygulanır. Her iki durumda da, programın bozulmuş durumda olması beklendiğinden hiçbir özel durum işleyicisi çağrılmaz. Bir hata ayıklayıcı varsa, işten çıkarılmadan önce programın durumunu inceleme fırsatı verilir.

Windows 8 ' de yerel hızlı hata mekanizması desteği başlatıldı. Hızlı başarısızlık yönergesini yerel olarak desteklemeyen Windows işletim sistemleri, genellikle bir erişim ihlali veya bir `UNEXPECTED_KERNEL_MODE_TRAP` hata denetimi olarak hızlı bir başarısızlık isteğini kabul eder. Bu gibi durumlarda, program hala sona erer, ancak hızlı şekilde gerekli değildir.

`__fastfail`yalnızca iç öğe olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__fastfail`|x86, x64, ARM, ARM64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
