---
description: 'Daha fazla bilgi edinin: Extract Işlevi'
title: Extract Işlevi
ms.date: 11/16/2016
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
ms.openlocfilehash: 4ae5e858c658d14e72db8740232b74935c655292
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259766"
---
# <a name="extract-function"></a>Extract Işlevi

**Ne:** Kodun bir parçasını kendi işlevine açmanızı sağlar.

**Ne zaman:** Başka bir işlevden çağrılması gereken, bazı işlevlerden varolan kodun bir parçası var.

**Neden:** Bu kodu kopyalayabilir/yapıştırabilir, ancak çoğaltmaya yol açabilir.  Daha iyi bir çözüm, bu parçayı, başka bir işlev tarafından serbestçe çağrılabilen kendi işlevine yeniden düzenlemeniz.

**Oluşturulacağı**

1. Ayıklanacak kodu vurgulayın:

   ![Vurgulanan kod](images/extractfunction_highlight.png)

1. Sonra, aşağıdakilerden birini yapın:
   * **Klavye**
     * **CTRL + R**, ardından **CTRL + M** tuşlarına basın.  (Klavye kısayolunuzun seçtiğiniz profile göre farklı olabileceğini unutmayın.)
     * **CTRL +** tuşlarına basın. **hızlı eylemleri ve yeniden düzenlemeler** menüsünü tetiklemek ve bağlam menüsünden **Işlevi Ayıkla (deneysel)** seçeneğini belirleyin.
   * **Fare**
     * **> Ayıkla (deneysel) > Düzenle** seçeneğini belirleyin.
     * Koda sağ tıklayın, **Hızlı Eylemler ve yeniden düzenlemeler** menüsünü seçin ve bağlam menüsünden **Işlevi Ayıkla (deneysel)** seçeneğini belirleyin.
     * ![ ](images/bulb.png) Sol kenar boşluğunda görüntülenen ampul simgesine tıklayın ve bağlam menüsünden **Işlevi Ayıkla (deneysel)** seçeneğini belirleyin.

1. **İşlevi/yöntemi Ayıkla (deneysel)** penceresinde, yeni işlev adını girin, kodun yerleştirilmesini istediğiniz yeri seçin ve **Tamam** düğmesine tıklayın.

   ![İşlev Ayıkla iletişim kutusu](images/extractfunction_dialog.png)

1. Yeni işlev, belirttiğiniz yerde, ilgili başlık dosyasında bir işlev prototipini ve bu işlevi çağırmak için özgün kod değiştirilir.

   ![İşlev sonucunu Ayıkla](images/extractfunction_result.png)
