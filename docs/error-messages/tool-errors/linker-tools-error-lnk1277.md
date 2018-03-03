---
title: "Bağlayıcı araçları hatası LNK1277 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3606207afc197dc26ac0540d476b74f52c0dc0a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277
Nesne kayıt pgd (dosya adı) bulunamadı  
  
 Kullanırken [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), yolun giriş .lib, def veya .obj dosyaları birinin üzerinde bunlar bulundu sırasında /LTCG:PGINSTRUMENT yolu farklıdır. Bu değişikliği LIB ortam değişkeni /LTCG:PGINSTRUMENT sonra açıklanması. Giriş dosyaları tam yolunu .pgd dosyasında depolanır.  
  
 /LTCG:PGOPTIMIZE girişleri /LTCG:PGINSTRUMENT aşamasına aynı olmasını gerektirir.  
  
 Bu uyarıyı çözmek için aşağıdakilerden birini yapın:  
  
-   /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın.  
  
-   LIB ortam değişkeni /LTCG:PGINSTRUMENT çalıştırdığınızda ne olduğu için değiştirin.  
  
 /LTCG:PGUPDATE kullanarak LNK1277 çözüm önerilmez.