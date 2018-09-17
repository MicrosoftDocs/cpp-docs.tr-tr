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
ms.openlocfilehash: 613a6357da969cb39d84d1f6e764f14112b3b6fc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712614"
---
# <a name="file-translation-constants"></a>Dosya Çeviri Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  

Çeviri modu sabitleri bu belirtin (**"b"** veya **"t"**). Modu erişim türünü belirten dizeyi dahildir (**"r"**, **"w"**, **"a"**, **"r +"**, **"w +"**, **"a +"**).  
  
Çeviri modları aşağıdaki gibidir:  
  
- **T**  

   Metin (çevrilmiş) modunda açar. Bu modda, return-satır başı/satır besleme (CR-LF) birleşimleri karakterlerine (LF) giriş çevrilir ve LF karakterleri çıkış CR-LF kombinasyonlarına çevrilir. Ayrıca, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma/yazma için açılmış dosyalarında `fopen` CTRL + Z dosya sonunda olup olmadığını denetler ve eğer mümkünse bunu kaldırır. Kullanıldığından yapıldığını `fseek` ve `ftell` CTRL + Z ile biten bir dosya içinde taşımak için işlevleri neden `fseek` dosyanın sonuna yakın yanlış davranmasına.  
  
   > [!NOTE]
   > **t** seçeneği ANSI standardı bir parçası değil `fopen` ve `freopen`. Bir Microsoft uzantısıdır ve ANSI taşınabilirliğinin istendiği durumlarda kullanılmamalıdır.  
  
- **b**  

   İkili (çevrilmemiş) modda açılır. Yukarıdaki Çeviriler bastırılır.  
  
Varsa **t** veya **b** verilmez *modu*, çeviri modu varsayılan modlu değişkeni tarafından tanımlanan [_fmode](../c-runtime-library/fmode.md). Metin ve ikili modlarda kullanma hakkında daha fazla bilgi için bkz. [metin ve ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)