---
title: Saklı Yordamları Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
ms.openlocfilehash: 2c0c1c71103384439d0b7b94f942e1b5a6d9e651
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536167"
---
# <a name="using-stored-procedures"></a>Saklı Yordamları Kullanma

Bir saklı yordam, bir veritabanında yürütülebilir bir nesnedir. Bir SQL komutu çağırmak için bir saklı yordamı çağırma benzerdir. (Yerine, yürütme veya istemci uygulamasındaki bir deyim hazırlanıyor) veri kaynağında depolanan yordamları kullanarak, daha yüksek performans, azaltılmış ağ yükünü ve geliştirilmiş tutarlılık ve doğruluk dahil olmak üzere çeşitli avantajlar sağlayabilir.

Bir saklı yordam (sıfır dahil), herhangi bir sayı olabilir giriş veya çıkış parametresi ve dönüş değeri geçirebilirsiniz. Belirli veri değerleri veya bir parametre işaretçisi kullanın ya da sabit kod parametre değerleri olabilir (bir soru işareti '?').

> [!NOTE]
>  CLR SQL Server saklı yordamları Visual C++ kullanılarak oluşturulan derlenmiş, ile `/clr:safe` derleyici seçeneği.

OLE DB sağlayıcısı için SQL Server (SQLOLEDB) depolanan yordamları kullanım verileri döndürmek için aşağıdaki mekanizmalarını destekler:

- Her **seçin** yordamındaki bir sonuç kümesi oluşturur.

- Yordamı, çıktı parametreleri aracılığıyla veri döndürebilir.

- Yordamın dönüş kodu bir tamsayı olabilir.

> [!NOTE]
> Sağlayıcının saklı yordamları desteklemediğinden, Jet için OLE DB sağlayıcısı ile saklı yordamlar kullanamazsınız; yalnızca sabitler, sorgu dizelerine izin verilir.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)