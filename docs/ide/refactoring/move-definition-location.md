---
title: Tanım konumunu Taşı | Microsoft Docs
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
ms.openlocfilehash: 5058e0b3bab1fb5fb5e8d52b55e3fa7c37fd8a4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430069"
---
# <a name="move-definition-location"></a>Tanım konumunu Taşı
**Ne:** hemen karşılık gelen bir üstbilgi dosyası için bir işlev tanımını Taşı olanak tanır.

**Ne zaman:** bir üstbilgi dosyasına taşımak istediğiniz bir işleviniz oldu.

**Neden:** işlevi el ile taşıyabilirsiniz, ancak bu özellik, otomatik olarak gerekirse üstbilgi dosyası oluşturma taşınır.

**Nasıl:**

1. Metin veya fare imlecinizi taşımak istediğiniz işlevin üzerine yerleştirin.

   ![Vurgulanmış kodu](images/movedefinition_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **tanım konumunu Taşı** bağlam menüsünden.
   * **Fare**
     * Sağ tıklayıp **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **tanım konumunu Taşı** bağlam menüsünden.

1. İşlevi, bir önizleme açılan pencerede görürsünüz ilgili başlık dosyası taşınır.  Üstbilgi dosyası mevcut değilse, bu da oluşturulacak ve projede yerleştirilir.

   ![Oluşturma bildirimi / tanımı neden](images/movedefinition_result.png)
