---
title: "Saf sanalların uygulamak | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f311c2e5832754bfd785084b9aa930b5dbe43845
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implement-pure-virtuals"></a>Saf sanalların uygulama
**Ne:** hemen bir sınıfta tüm saf sanal yöntemleri uygulamak için gereken kodu oluşturmanıza olanak sağlar. 

**Ne zaman:** saf sanal işlevlerle sınıfından devralan istiyor.  

**Neden:** bu özellik tüm yöntemi imzaları otomatik olarak oluşturur ancak tüm saf sanal işlevler birer birer kendiniz uygulamak.

**Nasıl:**

1. Metin veya fare imlecinizi saf sanal işlevler temel sınıfın uygulamak istediğinize sınıfı yerleştirin.

   ![Vurgulanmış kodu](images/virtuals_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **sınıfı için tüm saf sanalların uygulamak*ClassName*' ** ve bağlam menüsünden nerede  *ClassName* seçilen sınıfın adı.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **sınıfı için tüm saf sanalların uygulamak*ClassName*' ** ve bağlam menüsünden nerede  *ClassName* seçilen sınıfın adı.

1. Saf sanal yöntemi imzalar, otomatik olarak oluşturulan, uygulanması için hazır olacaktır.

   ![Saf sanalların sonuç uygulama](images/virtuals_result.png)
