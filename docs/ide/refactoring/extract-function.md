---
title: İşlev ayıklamak | Microsoft Docs
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
ms.openlocfilehash: 7fc4d48c972bca9352f326085574e4cf4df83aea
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33333163"
---
# <a name="extract-function"></a>Extract işlevi
**Ne:** kendi işlevdeki bir kod parçacığını kapatmanızı sağlar.

**Ne zaman:** başka bir işlevden çağrılması gereken bazı işlevi, varolan kod parçacığını sahip.  

**Neden:** , kopyalayıp bu kodu yapıştırın, ancak çoğaltma için neden.  Bu parça serbestçe herhangi bir işlev tarafından çağrılabilir kendi işlevi halinde yeniden düzenlemeniz daha iyi bir çözümdür.

**Nasıl:**

1. Ayıklanacak kod vurgula:

   ![Vurgulanmış kodu](images/extractfunction_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + M**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ayıklamak işlevi (Experimental)** ve bağlam menüsünden.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > Extract işlevi (Deneysel)**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **ayıklamak işlevi (Experimental)** ve bağlam menüsünden.
     * Tıklatın ![ampul](images/bulb.png) seçin ve sol kenar boşluğu içinde görünen simgesi **ayıklamak işlevi (Experimental)** ve bağlam menüsünden.

1. İçinde **ayıklama işlevi/yöntemi (Experimental)** penceresinde, yeni işlev adını girin, yerleştirilmesini kodu istediğiniz yeri seçin ve tıklatın **Tamam** düğmesi.  

   ![Extract işlevi işlevi](images/extractfunction_dialog.png)

1. Yeni işlev oluşturulacak burada işlev prototipi ilgili üstbilgi dosyasında belirtilen ve bu işlevi çağırmak için özgün kod değiştirilir.

   ![İşlev sonucuna Ayıkla](images/extractfunction_result.png)