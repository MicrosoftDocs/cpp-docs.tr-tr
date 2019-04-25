---
title: beklenmeyen (CRT)
ms.date: 11/04/2016
apiname:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 78538c0a10e183e72c742b041b297275c0859a03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155491"
---
# <a name="unexpected-crt"></a>beklenmeyen (CRT)

Çağrıları **sonlandırmak** veya işlevi kullanarak belirttiğiniz **set_unexpected**.

## <a name="syntax"></a>Sözdizimi

```C
void unexpected( void );
```

## <a name="remarks"></a>Açıklamalar

**Beklenmeyen** yordamı ile C++ özel durum işleme geçerli uygulama kullanılmaz. **Beklenmeyen** çağrıları **sonlandırmak** varsayılan olarak. Bu varsayılan davranışı özel sonlandırma işlevi yazma ve çağırma değiştirebilirsiniz **set_unexpected** bağımsız değişken olarak işlevinizi adı. **Beklenmeyen** bağımsız değişkeni olarak verilen son işlevi çağırır **set_unexpected**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**beklenmeyen**|\<EH.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırma](terminate-crt.md)<br/>
