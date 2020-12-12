---
description: 'Hakkında daha fazla bilgi edinin: _fwrite_nolock'
title: _fwrite_nolock
ms.date: 4/2/2020
api_name:
- _fwrite_nolock
- _o__fwrite_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fwrite_nolock
- fwrite_nolock
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
ms.openlocfilehash: 6b80933756c930403cbba464fb4921266b0d618f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273741"
---
# <a name="_fwrite_nolock"></a>_fwrite_nolock

İş parçacığını kilitlemeden verileri bir akışa yazar.

## <a name="syntax"></a>Sözdizimi

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Yazılacak verilere yönelik işaretçi.

*boyutla*<br/>
Bayt cinsinden öğe boyutu.

*biriktirme*<br/>
Yazılacak en fazla öğe sayısı.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

[Fwrite](fwrite.md)ile aynı.

## <a name="remarks"></a>Açıklamalar

Bu işlev, **fwrite**'un kilitleme olmayan bir sürümüdür. Bu, diğer iş parçacıklarının girişim tarafından korunmamasının dışında, **fwrite** ile aynıdır. Diğer iş parçacıklarını kilitleme yükünü karşılamadığından daha hızlı olabilir. Bu işlevi yalnızca tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Fread](fread.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
