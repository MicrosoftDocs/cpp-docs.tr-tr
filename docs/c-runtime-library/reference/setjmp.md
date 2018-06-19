---
title: setjmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- setjmp
apilocation:
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
apitype: DLLExport
f1_keywords:
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc4673485577f5a12024d31e94063c82a8c7b8c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407258"
---
# <a name="setjmp"></a>setjmp

Program geçerli durumunu kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>Parametreler

*Zarf*<br/>
Ortam depolandığı değişken.

## <a name="return-value"></a>Dönüş Değeri

Yığın ortamını kaydetme sonra 0 döndürür. Varsa **setjmp** sonucu olarak döndürür bir **longjmp** çağrısı, döndürdüğü **değeri** bağımsız değişkeni **longjmp**, veya **değeri**  bağımsız değişkeni **longjmp** 0 ' dır **setjmp** 1 döndürür. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

**Setjmp** işlevi kaydeder, daha sonra kullanarak geri yükleyebilirsiniz bir yığın ortamı **longjmp**. Birlikte kullanıldığında **setjmp** ve **longjmp** yerel olmayan yürütmek için bir yol sağlamak **goto**. Bunlar genellikle normal arama kullanmadan önce çağrılan bir yordam hata işleme veya kurtarma kodunda yürütme denetimi geçirmek için kullanılan veya kuralları döndürür.

Çağrı **setjmp** geçerli yığın ortamda kaydeder *env*. Sonraki çağrı **longjmp** kaydedilmiş ortamı geri yükler ve döndürür denetim noktası yalnızca karşılık gelen sonra **setjmp** çağırın. Denetim alma yordamı erişilebilir tüm değişkenleri (dışında yazmaç değişkenleri) sahip oldukları zaman değerlerini içeren **longjmp** çağrıldı.

Kullanmak mümkün değil **setjmp** yönetilen kod Yerelden atlamak için.

**Not** **setjmp** ve **longjmp** C++ nesne semantiği desteklemez. C++ programlarında C++ özel durum işleme mekanizması kullanın.

Daha fazla bilgi için bkz: [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setjmp**|\<setjmp.h'ı >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_fpreset](fpreset.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)<br/>
[_setjmp3](../../c-runtime-library/setjmp3.md)<br/>
