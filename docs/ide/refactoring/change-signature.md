---
title: İmzayı Değiştir
ms.date: 11/16/2016
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
ms.openlocfilehash: 776f777eb64128e9914e6d087551930593a490fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584047"
---
# <a name="change-signature"></a>İmzayı Değiştir
**Ne:** bir işlevin parametreleri değiştirmenize olanak tanır.

**Ne zaman:** yeniden düzenlemek, eklemek, kaldırmak veya çeşitli konumlarda kullanılmakta olan bir işlevin parametreleri değiştirmek istiyorsunuz.

**Neden:** el ile kendiniz, bu parametreleri değiştirmek ve daha sonra bu işleve yapılan tüm çağrılar bulun ve bunları tek tek değiştirmek, ancak hatalarına neden olabilir.  Bu yeniden düzenleme aracı görevi otomatik olarak gerçekleştirir.

**Nasıl:**

1. Adı değiştirmek için yöntemi veya kendi kullanımlarından metin veya fare imleci yerleştirin:

   ![Vurgulanmış kodu](images/changesignature_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + O**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **değişiklik imzası** bağlam menüsünden.
   * **Fare**
     * Seçin **Düzenle > Yeniden Düzenle > parametreleri yeniden Sırala**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **değişiklik imzası** bağlam menüsünden.

1. İçinde **değişiklik imzası** , açılan iletişim yöntem imzası değiştirmek için sağ tarafındaki düğmeleri kullanabilirsiniz:

   ![Değişiklik imzası iletişim](images/changesignature_dialog.png)

   | Düğme | Açıklama
   | ------ | ---
   | **Yukarı/Aşağı**    | Seçili parametreyi listede yukarı ve Aşağı Taşı
   | **Add**        | Listeye yeni bir parametre ekleyin
   | **Kaldır**     | Seçili parametreyi listeden kaldırın
   | **Değiştirme**     | Seçili parametre türünü değiştirerek değiştirme ad ve isteğe bağlıdır ve eklenen değeri olması
   | **Geri Al**     | Seçili parametreyi özgün durumuna geri yükleme
   | **Tümünü Geri Al** | Tüm parametreler için özgün durumuna geri yükleme

   > [!TIP]
   > Kullanım **Atla Önizleme başvuru değişiklikleri tüm başvurular onaylanırsa** ilk pencerelerinin Önizleme penceresini olmadan hemen değişiklikleri yapmak için onay kutusu.

   Ekliyor veya değiştiriyorsanız bir parametre, göreceğiniz **parametresi Ekle** veya **Düzenle parametresi** penceresi.

   ![Parametre Ekle/Değiştir](images/changesignature_addmodify.png)

   Burada, aşağıdakileri yapabilirsiniz:

   | Giriş | Açıklama
   | ----- | ---
   | **Türü**               | Parametre türü (int, çift, float, vs.)
   | **Ad**               | Parametrenin adı
   | **İsteğe bağlı parametre** | İsteğe bağlı olarak belirtilen parametre sağlar
   | **Eklenen değer**     | Burada parametre belirtilmediyse işlev çağrıları eklenen değer (yalnızca geçerli **Ekle**)
   | **Varsayılan değer**      | Arayan bir belirtmiyorsa işlev tarafından kullanılan değer (yalnızca geçerli **isteğe bağlı parametreler**)

1. Kullanım **arama kapsamı** değişiklikleri proje veya çözümün tamamını için geçerli olacaksa, seçmek için açılır.

1. İşlemi tamamladığınızda, basın **Tamam** değişiklik yapmak için düğme.  İstediğiniz değişiklikleri yapılan uygun şekilde emin olun.  Onay kutularını penceresinin üst yarısında etkinleştirmek veya devre dışı herhangi bir öğesinin yeniden adlandırılması için kullanın.

   ![Değişiklik imzası Önizleme](images/changesignature_preview.png)

1. Her şey iyi görünüyor, tıklayın **Uygula** düğmesi ve işlev, kaynak kodunuzu değiştirilir.

   ![Değişiklik imzası sonucu](images/changesignature_result.png)