---
title: Yeniden adlandırma | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a064527f6afcbf91be3fb4e51180be647c1f506
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33339819"
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
