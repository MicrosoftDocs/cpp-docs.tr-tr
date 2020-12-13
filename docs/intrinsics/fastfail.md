---
description: 'Hakkında daha fazla bilgi edinin: __fastfail'
title: __fastfail
ms.date: 09/02/2019
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: c7521f10dee7602fae3de5b2ac6fcc0245214bec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336996"
---
# <a name="__fastfail"></a>__fastfail

**Microsoft'a Özgü**

, Çağırma işlemini hemen en düşük yükle sonlandırır.

## <a name="syntax"></a>Sözdizimi

```C
void __fastfail(unsigned int code);
```

### <a name="parameters"></a>Parametreler

*kodudur*\
'ndaki `FAST_FAIL_<description>` Winnt. h veya WDM. h 'den, işlem sonlandırmasının nedenini gösteren bir sembolik sabit.

## <a name="return-value"></a>Döndürülen değer

`__fastfail`İç değer döndürmez.

## <a name="remarks"></a>Açıklamalar

`__fastfail`İç işlem, *hızlı bir başarısızlık* isteğine yönelik bir mekanizma sağlar. Bu işlem, acil bir işlem sonlandırma istemek için bozulmuş olabilecek bir işlemin yoludur. Bozuk program durumu ve kurtarma ötesinde yığın olabilecek kritik hata, normal özel durum işleme olanağı tarafından işlenemiyor. `__fastfail`En az ek yük kullanarak işlemi sonlandırmak için kullanın.

Dahili olarak, `__fastfail` çeşitli mimariye özgü mekanizmalar kullanılarak uygulanır:

|Mimari|Yönergenin|Kod bağımsız değişkeninin konumu|
|------------------|-----------------|-------------------------------|
|x86|Int 0x29|`ecx`|
|x64|Int 0x29|`rcx`|
|ARM|Opcode 0xDEFB|`r0`|
|ARM64|Opcode 0xF003|`x0`|

Hızlı bir başarısızlık isteği kendi içindedir ve genellikle yalnızca iki yönergelerin yürütülmesi gerekir. Hızlı bir başarısızlık isteği yürütüldükten sonra çekirdek, uygun eylemi gerçekleştirir. Kullanıcı modu kodunda, hızlı hata olayı ortaya çıktığında yönerge işaretçisinin ötesinde hiçbir bellek bağımlılığı yoktur. Ciddi bellek bozulması durumunda bile güvenilirliğini en üst düzeye çıkarır.

`code` `FAST_FAIL_<description>` Winnt. h veya WDM. h ' deki sembolik sabitlerden biri olan bağımsız değişkeni, hata koşulunun türünü açıklar. Hata raporlarına ortama özgü bir biçimde dahil değildir.

Kullanıcı modu hızlı başarısız istekler, 0xC0000409 özel durum kodu ve en az bir özel durum parametresi ile ikinci bir şans sürekliliği olmayan özel durum olarak görünür. İlk istisna parametresi `code` değeridir. Bu özel durum kodu, işlemin bozuk olduğu Windows Hata Bildirimi (WER) ve hata ayıklama altyapısına ve hataya yanıt olarak en düşük işlem içi eylemlerin alınması gerektiğini gösterir. Çekirdek modu hızlı başarısızlık istekleri, adanmış bir hata denetimi kodu `KERNEL_SECURITY_CHECK_FAILURE` (0x139) kullanılarak uygulanır. Her iki durumda da, programın bozulmuş durumda olması beklendiğinden hiçbir özel durum işleyicisi çağrılmaz. Bir hata ayıklayıcı varsa, işten çıkarılmadan önce programın durumunu inceleme fırsatı verilir.

Windows 8 ' de yerel hızlı hata mekanizması desteği başlatıldı. Hızlı başarısızlık yönergesini yerel olarak desteklemeyen Windows işletim sistemleri, genellikle bir erişim ihlali veya bir hata denetimi olarak hızlı bir başarısızlık isteğini kabul eder `UNEXPECTED_KERNEL_MODE_TRAP` . Bu gibi durumlarda, program hala sona erer, ancak hızlı şekilde gerekli değildir.

`__fastfail` yalnızca iç öğe olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__fastfail`|x86, x64, ARM, ARM64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
