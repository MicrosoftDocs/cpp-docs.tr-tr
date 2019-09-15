---
title: beklenmeyen (CRT)
ms.date: 11/04/2016
api_name:
- unexpected
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 796f5ddbf8467656b5430de1d504f162d891864d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957813"
---
# <a name="unexpected-crt"></a>beklenmeyen (CRT)

**Set_unexpected**kullanarak belirttiğiniz **sonlandırma** veya işlevi çağırır.

## <a name="syntax"></a>Sözdizimi

```C
void unexpected( void );
```

## <a name="remarks"></a>Açıklamalar

**Beklenmeyen** yordam C++ özel durum işlemenin geçerli uygulamasıyla kullanılmaz. **beklenmeyen** çağrılar varsayılan olarak **sonlandırılır** . Özel bir sonlandırma işlevi yazarak ve bağımsız değişkeni olarak işlevinizin adı ile **set_unexpected** çağırarak bu varsayılan davranışı değiştirebilirsiniz. **beklenmeyen** , **set_unexpected**için bağımsız değişken olarak verilen son işlevi çağırır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**bek**|\<Eh. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
