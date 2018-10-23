---
title: Oluşturma bildirimi / tanımı | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 6b1cdcb2-765e-4b93-8cef-92b861f64eba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21edf09eb78d339c06c709b06e8fe43ea72475c4
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808413"
---
# <a name="create-declaration--definition"></a>Oluşturma bildirimi / tanımı
**Ne:** anında bildirim veya bir işlev tanımı oluşturmanıza olanak tanır.

**Ne zaman:** bir bildirim ya da tam tersi gerektiren bir işleviniz oldu.

**Neden:** bildirimi/tanımı el ile oluşturabilirsiniz, ancak bu, otomatik olarak gerekirse başlık/kod dosyası oluşturma oluşturur.

**Nasıl:**

1. Metin veya fare imlecinizi bildirim veya tanım oluşturmak istediğiniz işlevin üzerine yerleştirin.

   ![Vurgulanmış kodu](images/createdefinition_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **oluşturma bildirimi / tanımı** bağlam menüsünden.
   * **Fare**
     * Sağ tıklayıp **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **oluşturma bildirimi / tanımı** bağlam menüsünden.

1. İşlev bildirimi/tanımı açılan Önizleme pencerede görürsünüz kaynak veya üst bilgi dosyası oluşturulur.  Kaynak veya üst dosya yoksa, bu da oluşturulacak ve projede yerleştirilir.

   ![Oluşturma bildirimi / tanımı neden](images/createdefinition_result.png)
