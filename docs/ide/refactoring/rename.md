---
title: "Yeniden adlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ca06ef5a11d674d35aff7276e14312c456c60e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rename"></a>Rename
**Ne:** alanları, yerel değişkenleri, yöntemleri, ad alanları, özellikleri ve türleri gibi kodu sembolleri tanımlayıcıları yeniden adlandır olanak sağlar.

**Ne zaman:** güvenli bir şekilde bir şey tüm örneklerini bulun ve yeni bir ad kopyala/yapıştır zorunda kalmadan yeniden adlandırmak istediğiniz.  

**Neden:** Kopyala ve yeni bir ad arasında projenin tamamında yapıştırma misiniz olasılıkla neden hatalar.  Bu yeniden düzenleme aracı doğru bir şekilde yeniden adlandırma eylemi gerçekleştirir.

**Nasıl:**

1. Vurgula veya metin imleci yeniden adlandırılacak öğesi içinde:

   ![Vurgulanmış kodu](images/rename_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + R**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > yeniden adlandırma**.
     * Kod sağ tıklatıp **yeniden adlandırma**.

1. İçinde **yeniden adlandırma** , açılır penceresi tıklatın ve seçili öğe için yeni bir ad girin **Önizleme** düğmesi.  Değişiklik **arama kapsamı** genişletebilir veya yeniden adlandırma kapsamını daraltmak gerekiyorsa.

   ![iletişim yeniden adlandırma](images/rename_dialog.png)

   > [!TIP]
   > Denetleyerek Önizleme atlayabilirsiniz **başvuruları tüm onaylanır Atla Önizleme değişirse** seçeneği.

1. Zaman **Değişiklikleri Önizle - yeniden adlandırma** penceresi görüntülenir, emin isteyen değişiklikleri yapılan uygun şekilde.  Etkinleştirmek veya devre dışı herhangi bir öğeyi yeniden adlandırmak için pencerenin üst yarısında onay kutularını kullanın.

   ![Önizleme yeniden adlandırma](images/rename_preview.png)

1. Her şey iyi göründüğünde tıklatın **Uygula** düğmesi ve öğesi, kaynak kodunuzda adlandırılacak.
