---
title: setjmp
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
ms.openlocfilehash: 4a88467f5b94ceae4281a35f1486380a877be2e5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948233"
---
# <a name="setjmp"></a>setjmp

Programın geçerli durumunu kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Parametreler

*env*<br/>
Ortamın depolandığı değişken.

## <a name="return-value"></a>Dönüş Değeri

Yığın ortamını kaydettikten sonra 0 döndürür. **Setjmp** bir `longjmp` çağrının sonucu olarak döndürülürse, *değer* bağımsız `longjmp`değişkenini döndürür ya da *değeri* `longjmp` 0 ise **setjmp** 1 döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**Setjmp** işlevi, daha sonra öğesini kullanarak `longjmp`geri yüklemek için bir yığın ortamı kaydeder. Birlikte kullanıldığında, **setjmp** ve `longjmp` yerel olmayan bir **goto**yürütmek için bir yol sağlar. Genellikle, normal çağırma veya döndürme kurallarını kullanmadan daha önce çağrılan bir yordamın hata işleme veya kurtarma koduna doğrudan yürütme denetimi geçirmek için kullanılır.

**Setjmp** çağrısı geçerli yığın ortamını *env*'ye kaydeder. Sonraki bir çağrı `longjmp` , kaydedilen ortamı geri yükler ve ilgili **setjmp** çağrısından hemen sonra denetim noktasına geri döndürür. Yordam alma denetimine erişilebilen tüm değişkenler (yazmaç değişkenleri hariç), çağrıldığında sahip `longjmp` oldukları değerleri içerir.

Yerel sunucudan yönetilen koda geçmek için **setjmp** kullanılması mümkün değildir.

**Microsoft 'a özgü**

Windows 'daki C++ Microsoft kodunda, **longjmp** , özel durum işleme kodu olarak aynı yığın geri sarma semantiğini kullanır. C++ Özel durumların ortaya çıkarılan aynı yerlerde kullanılması güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılarla birlikte gelir. Ayrıntılar için bkz. [longjmp](longjmp.md).

**SON Microsoft 'a özgü**

> [!NOTE]
> Taşınabilir C++ kodda, nesne semantiğini `setjmp` varsaymaz `longjmp` ve C++ destekleyebilirsiniz. Özellikle, `setjmp` **catch** ve **throw** / `longjmp` ile değiştirmek `setjmp` , tüm otomatik nesneler için önemsiz olmayan yıkıcıları çağıracağından, bir çağrı çiftinin tanımsız bir `longjmp` davranışı vardır. C++ Programlar ' da, C++ özel durum işleme mekanizmasını kullanmanızı öneririz.

Daha fazla bilgi için bkz. [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setjmp**|\<setjmp. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Fönayar](fpreset.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)
