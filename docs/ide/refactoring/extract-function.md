---
title: İşlevi Ayıkla | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca75ca3b69fb175bea160d7f2a35d36416ea2f5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441375"
---
# <a name="extract-function"></a>İşlevi Ayıkla
**Ne:** kendi işlevine kodun bir parçasını kapatmanızı sağlar.

**Ne zaman:** başka bir işlevden çağrılması gereken bazı işlevindeki mevcut kodun bir parçasını sahip.

**Neden:** , Kopyala/kod Yapıştır, ancak çoğaltma için neden.  Herhangi bir işlev tarafından çağrılabilen serbestçe kendi işlevine, parça yeniden düzenleme daha iyi bir çözümdür.

**Nasıl:**

1. Ayıklanacak kod vurgular:

   ![Vurgulanmış kodu](images/extractfunction_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + M**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **işlevi ayıklama (Deneysel)** bağlam menüsünden.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenleyin > ayıklayın işlevi (Deneysel)**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **işlevi ayıklama (Deneysel)** bağlam menüsünden.
     * Tıklayın ![ampul](images/bulb.png) seçin ve sol kenar boşluğu içinde görünen simge **işlevi ayıklama (Deneysel)** bağlam menüsünden.

1. İçinde **Extract işlevi/metodu (Deneysel)** penceresinde, yeni bir işlev adı girin, yerleştirilecek kodu istediğiniz yeri seçin ve tıklayın **Tamam** düğmesi.

   ![İşlev işlevi Ayıkla](images/extractfunction_dialog.png)

1. Yeni bir işlev oluşturulur bir işlev prototipi karşılık gelen bir üstbilgi dosyasında belirtilen ve bu işlevi çağırmak için özgün koda değiştirilecek.

   ![İşlev sonucuna ayıklayın](images/extractfunction_result.png)