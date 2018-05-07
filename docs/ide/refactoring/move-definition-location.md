---
title: Tanım konumu taşıma | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44211105429e33c136999a7877ac6ee42af29f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
