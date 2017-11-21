---
title: _CrtSetDumpClient | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs: C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 689d81d491b58755ca865c92cc79043d105c2be2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient
Dökümü uygulama tanımlı bir işlev yükler `_CLIENT_BLOCK` bellek blokları (yalnızca hata ayıklama sürümü) yazın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _CRT_DUMP_CLIENT _CrtSetDumpClient(   
   _CRT_DUMP_CLIENT dumpClient   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dumpClient`  
 C çalışma zamanı hata ayıklama bellek dökümü işlemine kanca yeni istemci tarafından tanımlanan bellek dökümü işlev.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceden tanımlanmış istemci bloğu döndüren dökümü işlevi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtSetDumpClient` İşlevi sağlayan kendi işlevi depolanan döküm nesnelere kanca uygulamaya `_CLIENT_BLOCK` bellek bloklara C çalışma zamanı hata ayıklama bellek dökümü işlemi. Sonuç olarak, her zaman bir hata ayıklama işlevi gibi dökümü [_CrtMemDumpAllObjectsSince](../../c-runtime-library/reference/crtmemdumpallobjectssince.md) veya [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) dökümleri bir `_CLIENT_BLOCK` bellek bloğu uygulamanın döküm işlevi de çağrılır. `_CrtSetDumpClient`bir uygulama bellek sızıntılarını algılama ve doğrulama veya depolanan veri içeriğini Raporlama ile kolay bir yöntemini sağlar `_CLIENT_BLOCK` engeller. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtSetDumpClient` ön işleme sırasında kaldırılır.  
  
 `_CrtSetDumpClient` İşlevi yükler belirtilen yeni uygulama tanımlı döküm işlevi `dumpClient` ve önceden tanımlanmış döküm işlevi döndürür. İstemci blok döküm işlevi örneği aşağıdaki gibidir:  
  
```  
void DumpClientFunction( void *userPortion, size_t blockSize );  
```  
  
 `userPortion` Bağımsız değişkeni bir işaretçidir bellek bloğu kullanıcı veri bölümü başlangıcını ve `blockSize` blok boyutu ayrılan belleğin bayt cinsinden belirtir. İstemci blok döküm işlevi döndürmelidir `void`. Geçirilir istemci döküm işlev işaretçisi `_CrtSetDumpClient` türü `_CRT_DUMP_CLIENT`, Crtdbg.h içinde tanımlanan:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );  
```  
  
 Üzerinde çalışan işlevler hakkında daha fazla bilgi için `_CLIENT_BLOCK` bellek blokları, bkz: [istemci blok kanca işlevleri](/visualstudio/debugger/client-block-hook-functions). [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md) işlevi, blok türleri ve alt türleri hakkında bilgi döndürmek için kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtSetDumpClient`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtGetDumpClient](../../c-runtime-library/reference/crtgetdumpclient.md)