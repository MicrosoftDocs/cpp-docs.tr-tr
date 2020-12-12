---
description: 'Hakkında daha fazla bilgi edinin: Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı'
title: Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.ui
helpviewer_keywords:
- MFC Application Wizard, user interface features
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
ms.openlocfilehash: ac2c3dc7881fd5e931539224bed121c617b940a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218517"
---
# <a name="user-interface-features-mfc-application-wizard"></a>Kullanıcı Arabirimi Özellikleri, MFC Uygulama Sihirbazı

Bu konuda, uygulamanızın görünümünü belirtmek için kullanabileceğiniz seçenekler açıklanmaktadır. Projeniz için kullanılabilir olan kullanıcı arabirimi özellikleri, MFC Uygulama Sihirbazı 'nın [uygulama türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında belirttiğiniz uygulamanın türüne bağlıdır. Örneğin, tek bir belge arabirim uygulaması oluşturursanız, alt çerçeve stilleri ekleyemezsiniz.

- **Ana çerçeve stilleri**

   Uygulamanızın ana pencere çerçevesinin özelliklerini ayarlar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Kalın çerçeve**|Boyutlandırma kenarlığı olan bir pencere oluşturur. Varsayılan.|
   |**Simge durumuna küçült**|Ana çerçeve penceresinde Simgeleştir kutusunu içerir. Varsayılan.|
   |**Ekranı Kapla kutusu**|Ana çerçeve penceresinde Büyüt kutusunu içerir. Varsayılan.|
   |**Küçültülmüş**|Ana çerçeve penceresini bir simge olarak açar.|
   |**Mediği**|Ana çerçeve penceresini, ekran tam boyutuna açar.|
   |**Sistem menüsü**|Ana çerçeve penceresinde bir sistem menüsü içerir. Varsayılan.|
   |**Hakkında kutusu**|Uygulama için bir **hakkında** kutusunu içerir. Kullanıcı bu kutuya uygulamanın **Yardım** menüsünden erişebilir. [Uygulama türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **iletişim kutusu tabanlı**' i seçmediğiniz takdirde varsayılan ve değiştirilemez.<br /><br /> **Göz önünde** Genellikle, kullanılamayan bir seçenek, sihirbazın, kullanılamayan öğenin onay kutusunun seçili veya temizlenmiş olup olmadığı, projenin bu seçeneği uygulamadığını gösterir. Bu durumda, ilk olarak projeyi bir iletişim kutusu olarak belirtmediğiniz ve sonra kutunun işaretini kaldırıp, sihirbaz projeye her zaman bir **hakkında** kutusunu ekler.|
   |**İlk durum çubuğu**|Uygulamanıza bir durum çubuğu ekler. Durum çubuğu, klavye Caps Lock, NUM LOCK ve SCROLL LOCK tuşları için otomatik göstergeler ve menü komutları ve araç çubuğu düğmeleri için Yardım dizelerini görüntüleyen bir ileti çizgisi içerir. Bu seçeneğe tıkladığınızda durum çubuğunu göstermek veya gizlemek için menü komutları da eklenir. Varsayılan olarak, bir uygulamanın bir durum çubuğu vardır. İletişim kutusu tabanlı uygulama türleri için kullanılamaz.|
   |**Pencereyi Böl**|Bir ayırıcı çubuğu sağlar. Ayırıcı çubuğu, uygulamanın ana görünümlerini böler. Birden çok belge arabirimi (MDI) uygulamasında, MDI alt çerçevesinin istemci penceresi bir ayırıcı penceresidir ve tek bir belge arabirimi (SDI) uygulaması ve birden çok üst düzey belge uygulamasında ana çerçevenin istemci penceresi bir Splitter penceresidir. İletişim kutusu tabanlı uygulama türleri için kullanılamaz.|

- **Alt çerçeve stilleri**

   Uygulamanızdaki alt çerçevelerin görünümünü ve başlangıç durumunu belirtir. Alt çerçeve stilleri yalnızca MDI uygulamaları için kullanılabilir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Alt simge durumuna küçültme kutusu**|Bir alt pencerenin simge durumuna küçültme düğmesine sahip olup olmadığını belirtir (varsayılan olarak etkindir).|
   |**Alt ekranı kaplama kutusu**|Bir alt pencerenin ekranı kapla düğmesine sahip olup olmadığını belirtir (varsayılan olarak etkindir).|
   |**Alt öğe ekranı kaplamış**|' Nin [ön Reatewindow](../../mfc/reference/cwnd-class.md#precreatewindow) üye işlevindeki bir alt pencerenin başlangıçta büyüerek, CS. style bayrağını WS_MAXIMIZE `CChildFrame` .|

- **Komut çubukları (menü/araç çubuğu/şerit)**

   Uygulamanızın menüler, araç çubukları ve/veya şerit içerip içermediğini gösterir. İletişim kutusu tabanlı uygulamalar için kullanılamaz.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Klasik menü kullan**|Uygulamanızın klasik, sürüklenebilir olmayan bir menü içerdiğini belirtir.|
   |**Klasik bir takma araç çubuğu kullan**|Uygulamanıza standart bir Windows araç çubuğu ekler. Araç çubuğu yeni bir belge oluşturmak için düğmeler içerir; belge dosyalarını açma ve kaydetme; metin kopyalamayı, yapıştırmayı veya yazdırmayı kesme; ve yardım moduna girer. Bu seçeneğin etkinleştirilmesi, araç çubuğunu göstermek veya gizlemek için de menü komutları ekler.|
   |**Tarayıcı stili araç çubuğu kullan**|Uygulamanıza Internet Explorer stili bir araç çubuğu ekler.|
   |**Menü çubuğu ve araç çubuğu kullan**|Uygulamanızın bir sürüklenebilir menü çubuğu ve bir araç çubuğu içerdiğini belirtir.|
   |**Kullanıcı tanımlı araç çubukları ve görüntüler**|Kullanıcının çalışma zamanında araç çubuğunu ve araç çubuğu görüntülerini özelleştirmesini sağlar.|
   |**Kişiselleştirilmiş menü davranışı**|Menüde açıldıklarında öğelerin tam listesini mi yoksa yalnızca kullanıcının en sık kullandığı komutları mı içerdiğini belirtir.|
   |**Şerit kullanma**|, Uygulamanızda bir menü çubuğu veya araç çubuğu yerine Office 2007 benzeri bir şerit kullanır.|

- **İletişim kutusu başlığı**

   Yalnızca [CDialog sınıfı](../../mfc/reference/cdialog-class.md)tabanlı uygulamalar için, bu başlık iletişim kutusunun başlık çubuğunda görüntülenir. Bu alanı düzenlemek için önce **uygulama türü** altında **iletişim kutusu tabanlı** seçeneğini belirlemelisiniz. Daha fazla bilgi için bkz. [uygulama türü, MFC Uygulama Sihirbazı](../../mfc/reference/application-type-mfc-application-wizard.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
