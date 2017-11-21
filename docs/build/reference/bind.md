---
title: "-BAĞLAMA | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bind
dev_langs: C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 64d3269bda732ad16941a433674ed1c1ec2bf6e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bind"></a>/BIND
```  
/BIND[:PATH=path]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek, bir yürütülebilir dosya veya DLL için alma adresi tablosunda giriş noktaları adreslerini ayarlar. Bir programın yükleme süresini azaltmak için bu seçeneği kullanın.  
  
 Programın yürütülebilir dosya ve DLL'ler belirtin *dosyaları* EDITBIN komut satırı bağımsız değişken. İsteğe bağlı *yolu*  /Bind bağımsız değişkeni belirtilen dosyalar tarafından kullanılan DLL'leri konumunu belirtir. Birden çok dizin noktalı virgülle ayırın (**;**). Varsa *yolu* belirtilmezse, EDITBIN PATH ortam değişkeninde belirtilen dizinleri arar. Varsa *yolu* belirtilirse, EDITBIN PATH değişkeni yok sayar.  
  
 Bir program yüklendiğinde varsayılan olarak, program yükleyicisi giriş noktaları adreslerini ayarlar. Bu işlem geçen süreyi, DLL'leri sayısı ve programa başvurulan giriş noktası sayısını bağlı olarak değişir. Bir program ile/Bind değiştirdiyseniz ve yürütülebilir dosyasını temel giderir ve onun DLL'leri ile zaten yüklenen DLL çakışmadığından varsa, işletim sisteminin bu adresleri ayarlamak gerekmez. Burada dosyaları yanlış dayalı bir durumda, işletim sistemi programın DLL'leri yeniden yerleştirir ve giriş noktası adresleri programın yükleme süresi ekleyen yeniden hesaplar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN seçenekleri](../../build/reference/editbin-options.md)