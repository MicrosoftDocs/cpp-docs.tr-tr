---
title: Imzayı Değiştir
ms.date: 11/16/2016
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
ms.openlocfilehash: 1599a7900e33db61994ea75581f9d87b1aee83f9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171911"
---
# <a name="change-signature"></a>Imzayı Değiştir

**Ne:** Bir işlevin parametrelerini değiştirmenize izin verir.

**Ne zaman:** Çeşitli konumlarda kullanılmakta olan bir işlevin parametrelerini yeniden sıralamak, eklemek, kaldırmak veya değiştirmek isteyebilirsiniz.

**Neden:** Bu parametreleri kendiniz el ile değiştirebilir ve sonra bu işleve yapılan tüm çağrıları bulabilir ve bunları tek tek değiştirebilir ancak bu hatalara neden olabilir.  Bu yeniden düzenleme aracı görevi otomatik olarak gerçekleştirir.

**Oluşturulacağı**

1. Metin veya fare imlecini değiştirmek için yöntemin adının içine veya kullanımlarından birine yerleştirin:

   ![Vurgulanan kod](images/changesignature_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavyenizdeki**
     * **CTRL + R**, ardından **CTRL + O**tuşlarına basın.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * **CTRL +** tuşlarına basın. **Hızlı Eylemler ve yeniden düzenlemeler** menüsünü tetiklemek ve bağlam menüsünden **imzayı Değiştir** ' i seçin.
   * **Tığında**
     * **Düzenle > yeniden düzenleme > parametreleri yeniden**düzenleyin ' i seçin.
     * Koda sağ tıklayın, **Hızlı Eylemler ve yeniden düzenlemeler** menüsünü seçin ve bağlam menüsünde **imzayı Değiştir** ' i seçin.

1. Açılan **Imza Değiştir** iletişim kutusunda, yöntem imzasını değiştirmek için sağ taraftaki düğmeleri kullanabilirsiniz:

   ![Değişiklik imzası iletişim](images/changesignature_dialog.png)

   | Düğme | Açıklama
   | ------ | ---
   | **Yukarı/aşağı**    | Seçili parametreyi listede yukarı ve Aşağı Taşı
   | **Add**        | Listeye yeni bir parametre Ekle
   | **Kaldır**     | Seçili parametreyi listeden kaldırın
   | **Değiştirebilirler**     | Seçilen parametreyi türünü, adını ve isteğe bağlı olup olmadığını ve eklenen değerin ne olacağını değiştirin
   | **Döndürülemiyor**     | Seçilen parametreyi özgün durumuna geri yükle
   | **Tümünü dön** | Tüm parametreleri özgün durumlarına geri yükle

   > [!TIP]
   > Önizleme penceresi ilk kez kullanıma açmadan değişiklikleri hemen yapmak için **tüm başvurular onaylanırsa, önizleme başvurusunu atla** onay kutusunu kullanın.

   Bir parametre eklerken veya değiştirirken parametre **Ekle** veya **parametreyi Düzenle** penceresi görüntülenir.

   ![Parametre Ekle/Değiştir](images/changesignature_addmodify.png)

   Burada, şunları yapabilirsiniz:

   | Girdi | Açıklama
   | ----- | ---
   | **Tür**               | Parametrenin türü (int, Double, float, vb.)
   | **Ad**               | Parametrenin adı
   | **İsteğe bağlı parametre** | İsteğe bağlı olarak belirtilen parametreyi yapar
   | **Eklenen değer**     | Parametrenin belirtilmediği, işleve yapılan herhangi bir çağrıya yerleştirilen değer (yalnızca **ekleme**için geçerlidir)
   | **Varsayılan değer**      | Çağıran bir tane belirtmezse işlev tarafından kullanılan değer (yalnızca **Isteğe bağlı parametreler**için geçerlidir)

1. Değişikliklerin projeye mi yoksa tüm çözüme mı uygulanacağını seçmek için **arama kapsamı** açılan öğesini kullanın.

1. İşiniz bittiğinde, değişiklikleri yapmak için **Tamam** düğmesine basın.  İstediğiniz değişikliklerin uygun şekilde yapıldığından emin olun.  Herhangi bir öğenin yeniden adlandırılmasını etkinleştirmek veya devre dışı bırakmak için pencerenin üst yarısında bulunan onay kutularını kullanın.

   ![Imza önizlemesini Değiştir](images/changesignature_preview.png)

1. Her şey iyi göründüğünde **Uygula** düğmesine tıklayın ve işlev kaynak kodunuzda değiştirilir.

   ![Imza sonucunu Değiştir](images/changesignature_result.png)
