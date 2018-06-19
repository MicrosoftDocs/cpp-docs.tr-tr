---
title: Bağlayıcı araçları hatası LNK1277 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec8f00793fcda748c60d9d8ea775611e3d025cd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298736"
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277
Nesne kayıt pgd (dosya adı) bulunamadı  
  
 Kullanırken [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), yolun giriş .lib, def veya .obj dosyaları birinin üzerinde bunlar bulundu sırasında /LTCG:PGINSTRUMENT yolu farklıdır. Bu değişikliği LIB ortam değişkeni /LTCG:PGINSTRUMENT sonra açıklanması. Giriş dosyaları tam yolunu .pgd dosyasında depolanır.  
  
 /LTCG:PGOPTIMIZE girişleri /LTCG:PGINSTRUMENT aşamasına aynı olmasını gerektirir.  
  
 Bu uyarıyı çözmek için aşağıdakilerden birini yapın:  
  
-   /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın.  
  
-   LIB ortam değişkeni /LTCG:PGINSTRUMENT çalıştırdığınızda ne olduğu için değiştirin.  
  
 /LTCG:PGUPDATE kullanarak LNK1277 çözüm önerilmez.