---
title: _open_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _open_osfhandle
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
- _open_osfhandle
- open_osfhandle
dev_langs: C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8d214df5d1e1cd3a48336723cecbf530402eafe3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="openosfhandle"></a>_open_osfhandle
C çalışma zamanı dosya tanımlayıcısı var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _open_osfhandle (  
   intptr_t osfhandle,  
   int flags   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `osfhandle`  
 İşletim sistemi dosya işleci.  
  
 `flags`  
 İzin verilen işlem türleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, `_open_osfhandle` C çalışma zamanı dosya tanımlayıcısı döndürür. Aksi takdirde, -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_open_osfhandle` İşlevi C çalışma zamanı dosya tanımlayıcısı ayırır ve tarafından belirtilen işletim sistemi dosya işleci ile ilişkilendirir `osfhandle`. `flags` Bağımsız değişkeni olan bir veya daha fazla Fcntl.h içinde tanımlanan bildirim sabitleri biçimlendirilmiş bir tamsayı ifade. İki veya daha fazla bildirim sabitleri forma kullanılan zaman `flags` bağımsız değişkeni, sabitleri bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ).  
  
 Fcntl.h aşağıdaki bildirim sabitleri tanımlar.  
  
 **_O_APPEND**  
 Dosya işaretçisini her yazma işleminden önce dosyanın sonuna yerleştirir.  
  
 **_O_RDONLY**  
 Yalnızca okuma dosyasını açar.  
  
 **_O_TEXT**  
 Dosya (çevrilmiş) metin modunda açılır.  
  
 **_O_WTEXT**  
 Dosya Unicode (çevrilmiş UTF-16) modunda açılır.  
  
 İle açılmış bir dosyada kapatmak için `_open_osfhandle`, çağrı `_close`. Temel alınan tanıtıcısı da çağrısıyla kapalı `_close`, Win32 işlevi çağırmak gerekli değildir `CloseHandle` özgün tutamacı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_open_osfhandle`|\<io.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)