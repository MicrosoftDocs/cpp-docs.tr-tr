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
ms.workload: cplusplus
ms.openlocfilehash: dbcd323292e301857c65d908047ab14948b86573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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