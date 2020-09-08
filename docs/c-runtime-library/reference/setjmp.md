---
title: setjmp
description: Setjmp için API başvurusu; Bu, programın geçerli durumunu kaydeder.
ms.date: 08/14/2018
api_name:
- setjmp
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 3ea08e5379433e313e08870f735322b7d985aa64
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555611"
---
# <a name="setjmp"></a>setjmp

Programın geçerli durumunu kaydeder.

## <a name="syntax"></a>Söz dizimi

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Parametreler

*env*<br/>
Ortamın depolandığı değişken.

## <a name="return-value"></a>Dönüş Değeri

Yığın ortamını kaydettikten sonra 0 döndürür. **Setjmp** bir çağrının sonucu olarak döndürülürse, `longjmp` *değer* bağımsız değişkenini döndürür `longjmp` ya da *değeri* `longjmp` 0 ise **setjmp** 1 döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**Setjmp** işlevi, daha sonra öğesini kullanarak geri yüklemek için bir yığın ortamı kaydeder `longjmp` . Birlikte kullanıldığında, **setjmp** ve `longjmp` yerel olmayan bir yürütme yolu sağlar **`goto`** . Genellikle, normal çağırma veya döndürme kurallarını kullanmadan daha önce çağrılan bir yordamın hata işleme veya kurtarma koduna doğrudan yürütme denetimi geçirmek için kullanılır.

**Setjmp** çağrısı geçerli yığın ortamını *env*'ye kaydeder. Sonraki bir çağrı, `longjmp` kaydedilen ortamı geri yükler ve ilgili **setjmp** çağrısından hemen sonra denetim noktasına geri döndürür. Yordam alma denetimine erişilebilen tüm değişkenler (yazmaç değişkenleri hariç), çağrıldığında sahip oldukları değerleri içerir `longjmp` .

Yerel sunucudan yönetilen koda geçmek için **setjmp** kullanılması mümkün değildir.

**Microsoft'a Özgü**

Windows 'daki Microsoft C++ kodunda, **longjmp** , özel durum işleme kodu olarak aynı yığın geri sarma semantiğini kullanır. C++ özel durumlarının ortaya çıkarılan aynı yerlerde kullanılması güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılarla birlikte gelir. Ayrıntılar için bkz. [longjmp](longjmp.md).

**SON Microsoft 'a özgü**

> [!NOTE]
> Taşınabilir C++ kodunda, `setjmp` `longjmp` C++ nesne semantiğini varsaymaz ve destekleyebilirsiniz. Özellikle, bir `setjmp` / `longjmp` çağrı çiftinin, ve ile değiştiriyorsanız tanımsız bir davranışı vardır `setjmp` `longjmp` **`catch`** ve **`throw`** herhangi bir otomatik nesne için tüm önemsiz olmayan yıkıcıları çağırır. C++ programlarında, C++ özel durum işleme mekanizmasını kullanmanızı öneririz.

Daha fazla bilgi için bkz. [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Fpreset](fpreset.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)
