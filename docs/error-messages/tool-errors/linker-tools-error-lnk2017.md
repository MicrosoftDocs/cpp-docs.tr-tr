---
title: "Bağlayıcı araçları hatası LNK2017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2017
dev_langs: C++
helpviewer_keywords: LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f1b588abe7bb222751506e21d90b4b8596b381f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2017"></a>Bağlayıcı Araçları Hatası LNK2017
'kesimine' /LARGEADDRESSAWARE:NO geçersiz 'simgesi' yeniden konumlandırma  
  
 32-bit adresleriyle 64 bit bir görüntü oluşturmaya çalışıyorsunuz. Bunu yapmak için şunları yapmalısınız:  
  
-   Bir sabit yük adresi kullanın.  
  
-   Görüntü 3 GB kısıtlayın.  
  
-   Belirtin [/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md).