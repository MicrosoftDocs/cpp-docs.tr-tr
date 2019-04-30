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
ms.openlocfilehash: ac893981ff8c697dc090f1e6ad5ac61886a69f99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395852"
---
# <a name="odbc-administrator"></a>ODBC Yöneticisi

ODBC Yöneticisi kaydeder ve yapılandırır [veri kaynakları](../../data/odbc/data-source-odbc.md) , kullanılabilir yerel olarak ya da bir ağ üzerinden. Sihirbazlar, kullanıcılarınızın veri kaynaklarına bağlanır, uygulamalarınızda kod oluşturmak için ODBC Yöneticisi tarafından sağlanan bilgileri kullanın.

MFC ODBC sınıfları veya MFC veri erişim nesnesi (DAO) sınıfları ile kullanmak için ODBC veri kaynağı ayarlamak için öncelikle kaydetmeniz ve veri kaynağını yapılandırın. Eklemek ve veri kaynakları kaldırmak için ODBC Yöneticisi'ni kullanın. ODBC sürücüsü bağlı olarak, yeni veri kaynakları oluşturabilirsiniz.

ODBC Yöneticisi, Kurulum sırasında yüklenir. Seçerseniz, **özel** yükleme ve herhangi bir ODBC sürücüsünü seçmediyseniz **veritabanı seçenekleri** iletişim kutusunda, gerekli dosyaları yeniden yüklemek için kurulumu çalıştırmanız gerekir.

Kurulum sırasında yüklemek istediğiniz ODBC sürücüleri seçin. Visual C++ Kurulum programını kullanarak Visual C++ ile birlikte gelen ek sürücüler daha sonra yükleyebilirsiniz.

Visual C++ ile gönderilen ODBC sürücüleri yüklemek istiyorsanız, sürücüyle Kurulum programını çalıştırmanız gerekir.

#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>Visual C++ ile birlikte gelen ODBC sürücülerini yüklemek için

1. Kurulum, Visual C++ dağıtım CD'SİNDEN çalıştırın.

   Açılış Kurulum programının iletişim kutusu görüntülenir.

1. Tıklayın **sonraki** ulaşana kadar her iletişim kutusunda **yükleme seçenekleri** iletişim kutusu. Seçin **özel**ve ardından **sonraki**.

1. Tüm onay kutularını temizleyin **Microsoft Visual C++ Kurulumu** iletişim kutusu dışındaki **veritabanı seçenekleri** onay kutusunu işaretleyin ve ardından **ayrıntıları** görüntülenecek**Veritabanı seçenekleri** iletişim kutusu.

1. NET **Microsoft Veri erişim nesneleri** onay kutusunu seçin **Microsoft ODBC sürücüleri** onay kutusunu işaretleyin ve ardından **ayrıntıları**.

   **Microsoft ODBC sürücüleri** iletişim kutusu görüntülenir.

1. Yükleyin ve ardından istediğiniz sürücüleri seçin **Tamam** iki kez.

1. Tıklayın **sonraki** yüklemeyi başlatmak için kalan iletişim kutularında. Kurulum, yükleme tamamlandığında size bildirir.

Sürücüleri yüklü olduğunda, ODBC Yöneticisi'ni kullanarak veri kaynağı yapılandırabilirsiniz. ODBC simgesi Denetim Masası'nda bulabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)