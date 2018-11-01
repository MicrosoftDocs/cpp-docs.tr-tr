---
title: MFC Veritabanı Uygulamasında Dosya Menüsü
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
ms.openlocfilehash: ce56dd5f04312ae9e7b7f747ce81cb704f3d085d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629209"
---
# <a name="file-menu-in-an-mfc-database-application"></a>MFC Veritabanı Uygulamasında Dosya Menüsü

Bir MFC veritabanı uygulaması oluşturma ve Serileştirme kullanmayın, Dosya menüsünden nasıl, açık, yakın yorumlamak, kaydetme ve Farklı Kaydet komutlarının hiç stil kılavuzları için bu soruyu olsa da, bazı öneriler şunlardır:

- Dosya menüsünün açık komutu tamamen ortadan kaldırır.

- Aç komutunu "Veritabanını Aç" olarak yorumlar ve kullanıcı uygulamanızı tanır veri kaynakları listesini gösterir.

- Yorumlar, belki de "profili açın." Aç komutu Seri hale getirilmiş bir dosyası açarak ancak dosyayı HIS dahil olmak üzere, kullanıcının tercihlerini gibi "kullanıcı profilini" bilgileri içeren seri hale getirilmiş bir belge depolamak için kullanır veya (parola isteğe bağlı olarak dışlayan) kendi oturum açma kimliği ve veri kaynağı kendisine en açık tut kısa bir süre önce kullanmış.

MFC Uygulama Sihirbazı, hiçbir belge ilgili dosya menü komutları ile bir uygulama oluşturulmasını destekler. Seçin **Ritabanı görünümü dosya desteği olmadan** seçeneğini **veritabanı desteği** sayfası.

Özel bir şekilde dosya menü komutu yorumlamak için bir veya daha fazla komut işleyicileri, çoğunlukla kılmalı, `CWinApp`-türetilmiş sınıf. Örneğin, tamamen kılarsanız `OnFileOpen` (uygulayan `ID_FILE_OPEN` komut) auto'yu "Veritabanını Aç:"

- Temel sınıf sürümü Remove() çağırmayın `OnFileOpen`, bu yana komutun varsayılan uygulama framework'ün tamamen değiştiriyor.

- İşleyici, bunun yerine veri kaynakları listeleyen bir iletişim kutusu görüntülemek için kullanın. Çağırarak bu tür bir iletişim kutusu görüntüleyebilir `CDatabase::OpenEx` veya `CDatabase::Open` parametresiyle **NULL**. Bu, kullanılabilir tüm veri kaynaklarına kullanıcının makinesine görüntüleyen bir ODBC iletişim kutusunu açar.

- Veritabanı uygulamaları genellikle tüm belgeyi kaydetmeyin nedeni büyük olasılıkla kaydetme kaldırmak istediğiniz ve profil bilgilerini depolamak için seri hale getirilmiş bir belge kullanmadığınız sürece uygulamaları kaydedin. Aksi takdirde, örneğin, "işlem işleme." Kaydet komutunu uygulayabilir. Bkz: [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md) bu komutları geçersiz kılma hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca Bkz.

[Seri Hale Getirme: Seri Hale Getirme ile Veritabanı giriş/çıkışı](../mfc/serialization-serialization-vs-database-input-output.md)

