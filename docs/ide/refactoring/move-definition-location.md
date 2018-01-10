---
title: "Tanım konumu taşıma | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 838f3d01f5e6d8612948304b80b79cf9c7cb4720
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="move-definition-location"></a>Taşıma tanımı konumu
**Ne:** hemen bir işlev tanımı ilgili üstbilgi dosyası taşımanıza olanak tanır.

**Ne zaman:** bir üstbilgi dosyası taşımak istediğiniz bir işleve sahip.  

**Neden:** işlevi el ile taşıyabilirsiniz, ancak bu özellik, otomatik olarak, gerekirse üstbilgi dosyası oluşturma taşınır.

**Nasıl:**

1. Metin veya fare imlecinizi taşımak istediğiniz işlevi yerleştirin.

   ![Vurgulanmış kodu](images/movedefinition_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **taşıma tanımı konumu** ve bağlam menüsünden.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **taşıma tanımı konumu** bağlam menüsünden.

1. İşlev açılan Önizleme penceresinde görürsünüz ilgili üstbilgi dosyası taşınır.  Üstbilgi dosyası mevcut değilse, onu da oluşturulacak ve projede yerleştirilir.

   ![Bildirim oluşturma / tanımı sonucu](images/movedefinition_result.png)
