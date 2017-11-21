---
title: "Çeviri modu sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
dev_langs: C++
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f5224064158dcbcb277524af21a0059a324fbc5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="translation-mode-constants"></a>Çeviri Modu Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `_O_BINARY` Ve `_O_TEXT` bildirim sabitleri belirlemek dosyaları çeviri modu (`_open` ve `_sopen`) veya akışlar için çeviri modu (`_setmode`).  
  
 İzin verilen değerler şunlardır:  
  
 `_O_TEXT`  
 Dosya (çevrilmiş) metin modunda açılır. Satır başı - yeni satır (CR-LF) birleşimleri giriş, bir tek yeni satır (LF) dönüştürülür. Satır besleme karakterler CR LF birleşimleri çıktıyı uygulamasına dönüştürülür. Ayrıca, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma ve okuma/yazma için açılmış dosyalarında `fopen` CTRL + Z dosya sonunda olup olmadığını denetler ve, mümkünse kaldırır. Bu kullanılarak yapılır, çünkü `fseek` ve `ftell` CTRL + Z ile biten bir dosya içinde taşımak için işlevleri neden olabilir `fseek` dosyanın sonuna yakın yanlış bir şekilde davranır.  
  
 `_O_BINARY`  
 Dosya ikili (untranslated) modunda açılır. Yukarıdaki çevirileri görüntülenmez.  
  
 `_O_RAW`  
 Aynı `_O_BINARY`. C 2.0 uyumluluk için desteklenir.  
  
 Daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [dosya çevirisi](../c-runtime-library/file-translation-constants.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_kurulum Aç, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_pipe](../c-runtime-library/reference/pipe.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_setmode](../c-runtime-library/reference/setmode.md)   
 [Genel sabitler](../c-runtime-library/global-constants.md)