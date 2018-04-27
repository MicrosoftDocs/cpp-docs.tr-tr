---
title: _fread_nolock_s2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fread_nolock_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fread_nolock_s
- stdio/_fread_nolock_s
dev_langs:
- C++
ms.assetid: 5badb9ab-11df-4e17-8162-30bda2a4572e
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 55259cabf4edcbda53845d5b041bc05f4e792bc7
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="freadnolocks"></a>_fread_nolock_s

Verileri başka bir iş parçacığı kilitlemeden bir akıştan okur. Bu sürümü [fread_nolock](fread-nolock.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t _fread_nolock_s(
   void *buffer,
   size_t bufferSize,
   size_t elementSize,
   size_t elementCount,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Verileri için depolama konumu.

*BufferSize*<br/>
Hedef arabelleğinin bayt cinsinden boyutu.

*elementSize*<br/>
Bayt cinsinden okumak için öğeyi boyutu.

*elementCount*<br/>
Okunacak öğe maksimum sayısı.

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bkz: [fread_s](fread-s.md).

## <a name="remarks"></a>Açıklamalar

Bu işlev bir kilitleme sürümüdür **fread_s**. Aynı **fread_s** dışında girişime diğer iş parçacıkları tarafından korunmuyor. Başka bir iş parçacığı kilitleme yükünü artırmak değil olduğundan daha hızlı olabilir. Tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işler burada gibi iş parçacığı bağlamlarda yalnızca bu işlevi kullanın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fread_nolock_s**|C: \<stdio.h >; C++: \<cstdio > veya \<stdio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
