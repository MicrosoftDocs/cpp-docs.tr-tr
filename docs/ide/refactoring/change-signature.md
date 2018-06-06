---
title: İmza değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 8daaa060-7305-4035-99d2-8b460b4f4454
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f913f0b3065b136f626ef15cc2a77dce8d0254f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33335097"
---
# <a name="change-signature"></a>Değişiklik imza
**Ne:** bir işlevin parametreleri değiştirmenize olanak tanır.

**Ne zaman:** yeniden sıralamak için eklemek, kaldırmak veya çeşitli konumlara kullanılmakta olan bir işlevin parametreleri değiştirmek istediğiniz.  

**Neden:** el ile kendiniz bu parametreleri değiştirmek ve daha sonra bu işlev tüm çağrıları bulmak ve onları tek tek değiştirmek, ancak hatalarına neden olabilir.  Bu yeniden düzenleme aracı görevi otomatik olarak gerçekleştirir.

**Nasıl:**

1. Metin veya fare imleci değiştirmek için yöntemi veya kendi kullanımlarından adını içine koyun:

   ![Vurgulanmış kodu](images/changesignature_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + O**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **değişiklik imza** ve bağlam menüsünden.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > parametreleri yeniden Sırala**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **değişiklik imza** ve bağlam menüsünden.

1. İçinde **değiştirmek imza** , POP iletişim yöntemini imza değiştirmek için sağ tarafta düğmeleri kullanabilirsiniz:

   ![İmza iletişim değiştirme](images/changesignature_dialog.png)

   | Düğme | Açıklama
   | ------ | ---
   | **Yukarı/Aşağı**    | Seçilen parametre listesi yukarı ve Aşağı Taşı
   | **Ekle**        | Yeni bir parametresi listeye ekleyin
   | **Kaldır**     | Seçili parametreyi listeden kaldırın
   | **Değiştirme**     | Seçilen parametre türünü değiştirerek değişiklik ad ve isteğe bağlıdır ve eklenen değeri olması
   | **Geri**     | Seçilen parametre özgün durumuna geri yükleme
   | **Tüm geri** | Tüm parametreleri orijinal durumuna geri yükleme

   > [!TIP]
   > Kullanım **Atla Önizleme başvuru yapılan tüm başvuruları onaylanır değişirse** ilk pencerelerinin önizleme penceresi olmadan hemen değişiklik yapmak için onay kutusunu.

   Ekleme ya da bir parametre değiştirme göreceğiniz **parametresi Ekle** veya **Düzenle parametresi** penceresi.

   ![Parametre ekleme/Değiştir](images/changesignature_addmodify.png)

   Burada, aşağıdakileri yapabilirsiniz:

   | Giriş | Açıklama
   | ----- | ---
   | **Türü**               | Parametrenin türü (int, çift, float, vb..)
   | **Ad**               | Parametrenin adı
   | **İsteğe bağlı parametre** | İsteğe bağlı olarak belirtilen parametre yapar
   | **Eklenen değer**     | Hiçbir parametre değil burada belirtilen işlev çağrıları içine eklenen değer (yalnızca **Ekle**)
   | **Varsayılan değer**      | Çağıran bir belirtmiyorsa işlev tarafından kullanılan değer (yalnızca **isteğe bağlı parametreler**)

1. Kullanım **arama kapsamı** değişiklikleri proje veya çözümün tamamı için uygularsanız seçmek için açılır.

1. İşiniz bittiğinde, basın **Tamam** değişiklik yapmak için düğmesi.  İsteğinde bulunduğunuzu değişiklikleri yapılan uygun şekilde emin olun.  Etkinleştirmek veya devre dışı herhangi bir öğeyi yeniden adlandırmak için pencerenin üst yarısında onay kutularını kullanın.

   ![İmza Önizleme değiştirme](images/changesignature_preview.png)

1. Her şey iyi göründüğünde tıklatın **Uygula** düğmesi ve işlev kaynak kodunuzda değişeceği.

   ![İmza sonuç değiştirme](images/changesignature_result.png)