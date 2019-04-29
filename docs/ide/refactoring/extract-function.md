---
title: İşlevi Ayıkla
ms.date: 11/16/2016
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
ms.openlocfilehash: ec3b9a0aeaef9e418b457bafdfb9bb1bbd2edffc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349374"
---
# <a name="extract-function"></a>İşlevi Ayıkla

**Ne:** Kodun bir parçasını kendi işlevine kapatmanızı sağlar.

**ne zaman:** Başka bir işlevden çağrılması gereken bazı işlevindeki mevcut kodun bir parçasını sahip.

**Neden:** Kopyala/kod Yapıştır, ancak çoğaltma için neden.  Herhangi bir işlev tarafından çağrılabilen serbestçe kendi işlevine, parça yeniden düzenleme daha iyi bir çözümdür.

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
