---
title: Rename
ms.date: 11/16/2016
ms.assetid: 64b42a88-3bd9-4399-8b96-75bceffc353b
ms.openlocfilehash: a747784f46341f130d1271fd0f15475b63d7b6d8
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692548"
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
