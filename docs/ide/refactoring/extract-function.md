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
ms.openlocfilehash: e032c2f1579294431b01d5a7695bf2c8a35aa421
ms.sourcegitcommit: 072e12d6b7a242765bdcc9afe4a14a284ade01fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50136126"
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

   ![İşlev iletişim ayıklayın](images/extractfunction_dialog.png)

1. Yeni bir işlev oluşturulur bir işlev prototipi karşılık gelen bir üstbilgi dosyasında belirtilen ve bu işlevi çağırmak için özgün koda değiştirilecek.

   ![İşlev sonucuna ayıklayın](images/extractfunction_result.png)
