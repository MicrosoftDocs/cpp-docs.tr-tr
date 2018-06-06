---
title: Bildirim oluşturma / tanımı | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60d583ec47a3f9c5b61599a5945e3cfa0d375b1d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33331289"
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
