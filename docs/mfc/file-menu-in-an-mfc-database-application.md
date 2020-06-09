---
title: MFC Veritabanı Uygulamasında Dosya Menüsü
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
ms.openlocfilehash: fbbb4382749278708e8e758f79a618d5cad0549e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615693"
---
# <a name="file-menu-in-an-mfc-database-application"></a>MFC Veritabanı Uygulamasında Dosya Menüsü

Bir MFC veritabanı uygulaması oluşturur ve serileştirme kullanmıyorsanız, bu soruya yönelik stil yönergeleri bulunmadığından Dosya menüsünde açık, kapalı, Kaydet ve farklı Kaydet komutlarını nasıl yorumlayacağınız aşağıda verilmiştir:

- Dosya menüsünün açık komutunu tamamen ortadan kaldırın.

- Open komutunu "veritabanı aç" olarak yorumlayın ve kullanıcıya uygulamanızın tanıdığı veri kaynaklarının bir listesini gösterin.

- Open komutunu, belki "profil aç" olarak yorumlayın. Seri hale getirilmiş bir dosyayı açmak için açık tutun, ancak oturum açma KIMLIĞI (isteğe bağlı olarak parolayı hariç) ve en son çalıştığı veri kaynağı dahil olmak üzere kullanıcının tercihleri gibi "Kullanıcı profili" bilgilerini içeren serileştirilmiş bir belgeyi depolamak için dosyayı kullanın.

MFC Uygulama Sihirbazı, belgeyle ilgili dosya menüsü komutları olmadan bir uygulama oluşturmayı destekler. **Veritabanı desteği** sayfasında **dosya desteği olmadan veritabanı görünümü** seçeneğini belirleyin.

Bir dosya menü komutunu özel bir şekilde yorumlamak için, çoğunlukla türetilmiş sınıfdaki bir veya daha fazla komut işleyicisini geçersiz kılmanız gerekir `CWinApp` . Örneğin, `OnFileOpen` `ID_FILE_OPEN` "veritabanını aç:" anlamına gelir ve bunu tamamen geçersiz kılarsınız (komutunu uygular)

- `OnFileOpen`Çerçevenin varsayılan uygulamasını tamamen değiştirdiğiniz için temel sınıf sürümünü çağırmayın.

- Veri kaynaklarını listeleme iletişim kutusunu göstermek için işleyicisini kullanın. NULL parametresini çağırarak veya girerek bu tür bir iletişim kutusunu görüntüleyebilirsiniz `CDatabase::OpenEx` `CDatabase::Open` . **NULL** Bu, kullanıcının makinesinde kullanılabilir tüm veri kaynaklarını görüntüleyen bir ODBC iletişim kutusu açar.

- Veritabanı uygulamaları genellikle belgenin tamamını kaydetmediği için, profil bilgilerini depolamak üzere seri hale getirilmiş bir belge kullanmadığınız sürece Kaydet ve farklı kaydet uygulamalarını da kaldırmak isteyeceksiniz. Aksi takdirde, Kaydet komutunu, örneğin "işleme işlemi" gibi uygulayabilirsiniz. Bu komutları geçersiz kılma hakkında daha fazla bilgi için bkz. [Teknik notun 22](tn022-standard-commands-implementation.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Seri Hale Getirme: Seri Hale Getirme ve Veritabanı Giriş/Çıkışı](serialization-serialization-vs-database-input-output.md)
