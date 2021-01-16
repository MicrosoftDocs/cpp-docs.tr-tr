---
title: setjmp
description: Setjmp için API başvurusu; Bu, programın geçerli durumunu kaydeder.
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0830cf253553523747a815efc950d4cf75b36647
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242650"
---
# `setjmp`

Programın geçerli durumunu kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Parametreler

*`env`*\
Ortamın depolandığı değişken.

## <a name="return-value"></a>Dönüş Değeri

Yığın ortamını kaydettikten sonra 0 döndürür. **`setjmp`** Bir çağrı nedeniyle döndürülürse, ' `longjmp` ın *değer* bağımsız değişkenini döndürür ya da `longjmp` *Value* bağımsız değişkeni `longjmp` 0 ise **`setjmp`** 1 değerini döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**`setjmp`** İşlevi, daha sonra öğesini kullanarak geri yüklemek için bir yığın ortamı kaydeder `longjmp` . Birlikte kullanıldığında **`setjmp`** ve `longjmp` yerel olmayan bir yöntem çalıştırmak için bir yol sağlar **`goto`** . Genellikle, normal çağırma veya döndürme kurallarını kullanmadan daha önce çağrılan bir yordamın hata işleme veya kurtarma koduna doğrudan yürütme denetimi geçirmek için kullanılır.

**`setjmp`** Geçerli yığın ortamını ' A kaydetme çağrısı *`env`* . Sonraki bir çağrı, `longjmp` kaydedilen ortamı geri yükler ve ilgili çağrıdan hemen sonra denetim noktasına geri döndürür **`setjmp`** . Yordam alma denetimine erişilebilen tüm değişkenler (yazmaç değişkenleri hariç), çağrıldığında sahip oldukları değerleri içerir `longjmp` .

**`setjmp`** Yerelden yönetilen koda geçmek için kullanılması mümkün değildir.

**Microsoft'a Özgü**

Windows 'daki Microsoft C++ kodunda, **`longjmp`** özel durum işleme kodu olarak aynı yığın geri sarma semantiğini kullanır. C++ özel durumlarının ortaya çıkarılan aynı yerlerde kullanılması güvenlidir. Ancak, bu kullanım taşınabilir değildir ve bazı önemli uyarılarla birlikte gelir. Ayrıntılar için bkz [`longjmp`](longjmp.md) ..

**SON Microsoft 'a özgü**

> [!NOTE]
> Taşınabilir C++ kodunda, `setjmp` `longjmp` C++ nesne semantiğini varsaymaz ve destekleyebilirsiniz. Özellikle, bir `setjmp` / `longjmp` çağrı çiftinin, ve ile değiştiriyorsanız tanımsız bir davranışı vardır `setjmp` `longjmp` **`catch`** ve **`throw`** herhangi bir otomatik nesne için tüm önemsiz olmayan yıkıcıları çağırır. C++ programlarında, C++ özel durum işleme mekanizmasını kullanmanızı öneririz.

Daha fazla bilgi için bkz [. `setjmp` ve `longjmp` kullanma ](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`setjmp`**|\<setjmp.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

İçin örneğe bakın [`_fpreset`](fpreset.md) .

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)\
[`longjmp`](longjmp.md)
