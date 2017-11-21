---
title: "Bağlayıcı araçları hatası LNK1277 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1277
dev_langs: C++
helpviewer_keywords: LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 868fb4ef472aaf80242c276a9052562779da745c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277
Nesne kayıt pgd (dosya adı) bulunamadı  
  
 Kullanırken [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), yolun giriş .lib, def veya .obj dosyaları birinin üzerinde bunlar bulundu sırasında /LTCG:PGINSTRUMENT yolu farklıdır. Bu değişikliği LIB ortam değişkeni /LTCG:PGINSTRUMENT sonra açıklanması. Giriş dosyaları tam yolunu .pgd dosyasında depolanır.  
  
 /LTCG:PGOPTIMIZE girişleri /LTCG:PGINSTRUMENT aşamasına aynı olmasını gerektirir.  
  
 Bu uyarıyı çözmek için aşağıdakilerden birini yapın:  
  
-   /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın.  
  
-   LIB ortam değişkeni /LTCG:PGINSTRUMENT çalıştırdığınızda ne olduğu için değiştirin.  
  
 /LTCG:PGUPDATE kullanarak LNK1277 çözüm önerilmez.