---
title: fwrite | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fwrite
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
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5328ce6851ceb61ad3260760e95cd329ee064
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fwrite"></a>fwrite
Verileri bir akışa yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t fwrite(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Yazılacak veriler işaretçi.  
  
 `size`  
 Bayt olarak öğe boyutu.  
  
 `count`  
 Yazılacak öğe maksimum sayısı.  
  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `fwrite` tam sayı döndürür gerçekte yazılan öğeleri, hangi olabilir değerinden `count` bir hata oluşursa. Ayrıca, bir hata oluşursa, dosya konumu göstergesi belirlenemiyor. Her iki `stream` veya `buffer` null işaretçi veya tek sayıda yazılacak bayt Unicode modda belirtilirse, işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `fwrite` İşlevi Yazar kadar `count` öğeleri, `size` uzunluğu her gelen `buffer` çıktısına `stream`. İle ilişkili dosya işaretçisini `stream` (varsa) tarafından gerçekten yazılan bayt sayısı artar. Varsa `stream` açıldığında metin modunda bir satır başı ile - satır besleme çifti her satır besleme değiştirilir. Değiştirme dönüş değeri üzerinde etkisi yoktur.  
  
 Zaman `stream` Unicode çeviri modunda açılmış — Örneğin, varsa `stream` çağırarak açılan `fopen` ve içeren bir mod parametresini kullanarak `ccs=UNICODE`, `ccs=UTF-16LE`, veya `ccs=UTF-8`, veya bir Unicode modu değiştirilirse Çeviri modu kullanarak `_setmode` ve içeren bir mod parametresi `_O_WTEXT`, `_O_U16TEXT`, veya `_O_U8TEXT`—`buffer` bir dizi için bir işaretçi olarak yorumlanır `wchar_t` UTF-16 veri içeren. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.  
  
 Bu işlev çağıran iş parçacığı kilitler, iş parçacığı demektir. Kilitleme olmayan bir sürümü için bkz: `_fwrite_nolock`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fwrite`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [fread](../../c-runtime-library/reference/fread.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_fwrite_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [_write](../../c-runtime-library/reference/write.md)