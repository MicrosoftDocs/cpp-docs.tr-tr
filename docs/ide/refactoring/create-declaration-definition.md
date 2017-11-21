---
title: "Bildirim oluşturma / tanımı | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 25f622cbd71195e75907b113e12e4d40ef0ec912
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="create-declaration--definition"></a>Bildirim oluşturma / tanımı
**Ne:** hemen bildiriminde ya da bir işlev tanımı oluşturmanıza olanak sağlar.

**Ne zaman:** delcaration ya da tam tersini gerektiren bir işleve sahip.  

**Neden:** bildirimi/tanımı el ile oluşturabilirsiniz, ancak bu, otomatik olarak, gerekirse üstbilgi/kod dosyası oluşturma oluşturur.

**Nasıl:**

1. Metin veya fare imlecinizi bildirim veya tanımı oluşturmak istediğiniz işlevi yerleştirin.

   ![Vurgulanmış kodu](images/createdefinition_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **bildirimi oluşturma / tanımı** ve bağlam menüsünden.
   * **Fare**
     * Sağ tıklatın ve seçin **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **bildirimi oluşturma / tanımı** ve bağlam menüsünden.

1. İşlevin bildirimi/tanımı açılan Önizleme penceresinde görürsünüz kaynak veya üstbilgi dosyası oluşturulur.  Kaynak veya üst bilgi dosyası yoksa, bu da oluşturulacak ve projede yerleştirilir.

   ![Bildirim oluşturma / tanımı sonucu](images/createdefinition_result.png)
