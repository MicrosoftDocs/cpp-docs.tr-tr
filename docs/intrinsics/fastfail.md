---
title: __fastfail | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6699585db899fc2601ac4945c4b2c57edbf5f309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379183"
---
# <a name="fastfail"></a>__fastfail

**Microsoft'a özgü**

Çağırma işlemi en az yük ile hemen sonlanır.

## <a name="syntax"></a>Sözdizimi

```
void __fastfail(unsigned int code);
```

#### <a name="parameters"></a>Parametreler

*Kod*<br/>
[in] A `FAST_FAIL_<description>` winnt.h veya işlem sonlandırma nedenini gösteren wdm.h sembolik sabiti.

## <a name="return-value"></a>Dönüş Değeri

`__fastfail` İç sonuç döndürmez.

## <a name="remarks"></a>Açıklamalar

`__fastfail` İç bir mekanizma sağlar bir *hızlı başarısız* isteği — istek anında işlem sonlandırma için olası bozuk bir işlem için bir yol. Program durumunu ve kurtarma ötesinde yığın bozulmuş olabilir, kritik hatalara tesis normal özel durum işleme tarafından işlenemez. Kullanım `__fastfail` minimum ek yük kullanarak işlemi sonlandırılamıyor.

Dahili olarak `__fastfail` mimariye özgü çeşitli mekanizmalar kullanılarak uygulanır:

|Mimari|Yönerge|Kod bağımsız değişken konumu|
|------------------|-----------------|-------------------------------|
|x86|int 0x29|ecx|
|X64|int 0x29|rcx|
|ARM|0xDEFB opcode|r0|

Hızlı başarısız istek bağımsızdır ve bu normalde yalnızca iki yönergeleri yürütmek için gerektirir. Hızlı başarısız istek yürütüldü sonra çekirdek, daha sonra uygun tedbiri alır. Kullanıcı modu kodunda var. yönerge işaretçisini ötesinde bellek bağımlılık hızlı başarısız olayı oluşturulduğunda Ciddi Bellek Bozulması olsa bile bu ve güvenilirliği en üst düzeye çıkarır.

`code` Bağımsız değişken — birini `FAST_FAIL_<description>` winnt.h veya hata durumu türünü wdm.h—describes sembolik sabit değerler ve ortama özgü bir şekilde hata raporları eklenmiştir.

Kullanıcı modu hızlı başarısız istekleri, ikinci bir şans edilemeyecek özel durum 0xC0000409 özel durum kodu ile en az bir özel durum parametresi olarak görünür. İlk özel durum parametresi `code` değeri. Windows hata bildirimi (WER) ve işlem bozuk ve en az işlem içi Eylemler hatası için yanıt alınıp hata ayıklama altyapısı bu özel durum kodu gösterir. Çekirdek modu hızlı başarısız istekleri, bir özel hata denetimi kod kullanarak uygulanır `KERNEL_SECURITY_CHECK_FAILURE` (0x139). Program, bozuk bir durumda olması beklenir çünkü her iki durumda da, hiçbir özel durum işleyicileri çağrılır. Bir hata ayıklayıcı varsa, sona ermeden önce program durumunu inceleyebilir fırsatı verilir.

Windows 8'de yerel hızlı başarısız mekanizması desteği başladı. Erişim ihlali veya olarak hızlı başarısız yönerge yerel olarak desteklemeyen Windows işletim sistemleri hızlı başarısız istek genellikle işlemek bir `UNEXPECTED_KERNEL_MODE_TRAP` hata denetimi. Bu gibi durumlarda sonlandırılmış yine de, ancak bu şart değildir hızlı bir şekilde programdır.

`__fastfail` yalnızca bir iç öğe olarak kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__fastfail`|x86, x 64, ARM|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)