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
ms.openlocfilehash: cb2d07ab7d7434bdf06ddb8f004881289492882a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
