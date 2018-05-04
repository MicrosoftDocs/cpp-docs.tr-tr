---
title: Dosya çeviri sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.constants.file
dev_langs:
- C++
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 881402933978f5fe714a9b1950a9eade01494c79
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="file-translation-constants"></a>Dosya Çeviri Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çeviri modu bu sabitleri belirtin (**"b"** veya **"t"**). Mod erişim türünü belirleyerek dizesine dahil (**"r"**, **"w"**, **"a"**, **"r +"**, **"w +"**, **"bir +"**).  
  
 Çeviri modları aşağıdaki gibidir:  
  
 **T**  
 Metin (çevrilmiş) modunda açılır. Bu modda, satır başı-return/satır besleme (CR-LF) birleşimleri giriş üzerinde tek satır olan (LF) beslemeleri uygulamasına dönüştürülür ve LF karakterler CR LF birleşimleri çıktıyı uygulamasına dönüştürülür. Ayrıca, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma/yazma için açılmış dosyalarında `fopen` CTRL + Z dosya sonunda olup olmadığını denetler ve, mümkünse kaldırır. Bu kullanılarak yapılır, çünkü `fseek` ve `ftell` CTRL + Z ile biten bir dosya içinde taşımak için işlevleri neden olabilir `fseek` dosyanın sonuna yakın yanlış bir şekilde davranır.  
  
> [!NOTE]
>  **t** seçeneği için standart ANSI parçası değil `fopen` ve `freopen`. Bir Microsoft uzantısıdır ve burada ANSI taşınabilirlik istenen kullanılmamalıdır.  
  
 **b**  
 İkili (untranslated) modunda açılır. Yukarıdaki çevirileri görüntülenmez.  
  
 Varsa **t** veya **b** verilmemiştir *modu*, çeviri modu varsayılan mod değişkeni tarafından tanımlanan [_fmode](../c-runtime-library/fmode.md). Metin ve ikili modlarda kullanma hakkında daha fazla bilgi için bkz: [metin ve ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)