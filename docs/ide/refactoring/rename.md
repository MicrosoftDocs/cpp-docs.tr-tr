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
ms.openlocfilehash: 7a00eed341e0fc1ca8573e2f66744ea04055f259
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399218"
---
# <a name="rename"></a>Rename
**Ne:** alanlar, yerel değişkenler, yöntemleri, ad alanları, özellikler ve türler gibi kod simgeleri tanımlayıcıları yeniden adlandırın olanak tanır.

**Ne zaman:** güvenli bir şekilde bir şey tüm örneklerini bulun ve yeni adı kopyala/yapıştır gerekmeden yeniden adlandırmak istiyor.

**Neden:** kopyalayıp yeni bir ad, bir projenin tamamı yapıştırarak musunuz büyük olasılıkla hatalara neden.  Bu yeniden düzenleme aracı doğru yeniden adlandırma eylemi gerçekleştirir.

**Nasıl:**

1. Vurgulama veya yeniden adlandırılacak öğe metin imleci yerleştirin:

   ![Vurgulanmış kodu](images/rename_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + R**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
   * **Fare**
     * Seçin **Düzenle > yeniden düzenleyin > Yeniden Adlandır**.
     * Kod sağ tıklayıp **Yeniden Adlandır**.

1. İçinde **Yeniden Adlandır** , açılır penceresini tıklatın ve seçili öğe için yeni bir ad girin **Önizleme** düğmesi.  Değişiklik **arama kapsamı** yeniden adlandırma kapsamını daraltmak veya genişletmek istiyorsanız.

   ![yeniden adlandırma iletişim kutusu](images/rename_dialog.png)

   > [!TIP]
   > Önizleme denetleyerek atlayabilirsiniz **Atla Önizleme değişiklikleri başvurular tüm onaylanırsa** seçeneği.

1. Zaman **Değişiklikleri Önizle - Yeniden Adlandır** penceresi görüntülenirse, sağlamak istediğiniz değişiklikleri uygun şekilde yapılmıştır.  Onay kutularını penceresinin üst yarısında etkinleştirmek veya devre dışı herhangi bir öğesinin yeniden adlandırılması için kullanın.

   ![Önizleme yeniden adlandır](images/rename_preview.png)

1. Her şey iyi görünüyor, tıklayın **Uygula** düğmesi ve öğenin kaynak kodunuzu yeniden adlandırılacak.
