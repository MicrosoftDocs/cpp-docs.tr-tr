---
title: ODBC Yöneticisi
ms.date: 11/04/2016
helpviewer_keywords:
- installing ODBC
- ODBC data sources [C++], ODBC Administrator
- ODBC drivers [C++], installing
- ODBC [C++], ODBC Administrator
- Administrator in ODBC
- administration ODBC Administrator
- ODBC Administrator [C++]
- drivers [C++], ODBC
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
ms.openlocfilehash: 9e88492919eac80a4f3db2f94202d49011aa69de
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213206"
---
# <a name="odbc-administrator"></a>ODBC Yöneticisi

ODBC Yöneticisi, yerel olarak ya da bir ağ üzerinden kullanabileceğiniz [veri kaynaklarını](../../data/odbc/data-source-odbc.md) kaydeder ve yapılandırır. Sihirbazlar, uygulamalarınızda kullanıcılarınızı veri kaynaklarına bağlayan kod oluşturmak için ODBC Yöneticisi tarafından sağlanan bilgileri kullanır.

MFC ODBC sınıfları veya MFC veri erişim nesnesi (DAO) sınıfları ile kullanmak üzere bir ODBC veri kaynağı ayarlamak için, önce veri kaynağını kaydetmeniz ve yapılandırmanız gerekir. Veri kaynaklarını eklemek ve kaldırmak için ODBC Yöneticisi 'ni kullanın. ODBC sürücüsüne bağlı olarak, yeni veri kaynakları da oluşturabilirsiniz.

ODBC Yöneticisi kurulum sırasında yüklenir. **Özel** yükleme ' yi seçer ve **veritabanı seçenekleri** ILETIŞIM kutusunda herhangi bir ODBC sürücüsü seçmediyseniz, gerekli dosyaları yüklemek için kurulum 'u yeniden çalıştırmanız gerekir.

Kurulum sırasında, yüklemek istediğiniz ODBC sürücülerini seçersiniz. Daha sonra Visual C++ C++ Kurulum programını kullanarak görsele gönderilen ek sürücüleri yükleyebilirsiniz.

Görsele C++teslım olmayan ODBC sürücülerini yüklemek istiyorsanız, sürücüye eşlik eden Kurulum programını çalıştırmanız gerekir.

#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>Görsele gönderilen ODBC sürücülerini yüklemek içinC++

1. Kurulum 'U görsel C++ dağıtım CD 'nizden çalıştırın.

   Kurulum programındaki açma iletişim kutusu görüntülenir.

1. **Yükleme seçenekleri** iletişim kutusuna ulaşana kadar her Iletişim kutusunda **İleri** ' ye tıklayın. **Özel**' i seçin ve ardından **İleri**' ye tıklayın.

1. **Veritabanı seçenekleri** onay kutusu dışında **Microsoft görsel C++ kurulum** iletişim kutusundaki tüm onay kutularını temizleyin ve ardından **veritabanı seçenekleri** iletişim kutusunu göstermek için **Ayrıntılar** ' a tıklayın.

1. **Microsoft veri erişim nesneleri** onay kutusunu temizleyin, **Microsoft ODBC sürücüleri** onay kutusunu seçin ve ardından **Ayrıntılar**' a tıklayın.

   **MICROSOFT ODBC sürücüleri** iletişim kutusu görüntülenir.

1. Yüklemek istediğiniz sürücüleri seçin ve ardından iki kez **Tamam** ' a tıklayın.

1. Yüklemeyi başlatmak için kalan iletişim kutularında **İleri** ' ye tıklayın. Yükleme tamamlandığında kurulum size bildirir.

Sürücüler yüklendiğinde, ODBC Yöneticisi 'ni kullanarak veri kaynağını yapılandırabilirsiniz. ODBC simgesini Denetim Masası 'nda bulabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)
