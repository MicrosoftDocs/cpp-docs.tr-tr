---
title: "İşlev ayıklamak | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd91da5296df92103f3d10fd399bd7d53bc57b5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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