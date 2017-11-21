---
title: "LIB giriş dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f956dedb8be270eb9974fa035d38e7fbb6714499
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="lib-input-files"></a>LIB Giriş Dosyaları
LIB tarafından beklenen giriş dosyaları aşağıdaki tabloda gösterildiği gibi çünkü kullanılıyor, modunu bağlıdır.  
  
|Mod|Giriş|  
|----------|-----------|  
|Varsayılan (derleme veya bir kitaplık değiştirme)|COFF nesne (.obj) dosyaları, COFF kitaplıklarını (.lib), 32-bit nesne modeli biçimi (OMF) nesne (.obj) dosyaları|  
|/ Extract sahip bir üye ayıklanıyor|COFF kitaplık (.lib)|  
|Bir verme dosya oluşturup/def kitaplıkla alma|Modül-tanımlama (.def) dosyası, COFF nesne (.obj) dosyaları, COFF kitaplıklarını (.lib), 32-bit OMF nesne (.obj) dosyaları|  
  
> [!NOTE]
>  OMF kitaplıkları LIB 16-bit sürümü ile oluşturulmuş LIB 32-bit sürümünü girdi olarak kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB'e genel bakış](../../build/reference/overview-of-lib.md)