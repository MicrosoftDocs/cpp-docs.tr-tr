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
ms.openlocfilehash: 436c796b24b0fa498f2b3f45e848392635b22a34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376034"
---
# <a name="using-stored-procedures"></a>Saklı Yordamları Kullanma

Depolanan yordam, veritabanında depolanan yürütülebilir bir nesnedir. Depolanmış yordamı çağırmak, SQL komutunu çağırmaya benzer. Veri kaynağında depolanan yordamları kullanmak (istemci uygulamasında bir bildirimi yürütmek veya hazırlamak yerine) daha yüksek performans, azaltılmış ağ yükü ve geliştirilmiş tutarlılık ve doğruluk dahil olmak üzere çeşitli avantajlar sağlayabilir.

Depolanan yordam, herhangi bir sayıda (sıfır dahil) giriş veya çıkış parametrelerine sahip olabilir ve bir dönüş değerini geçebilir. Parametre değerlerini belirli veri değerleri olarak sabit kodlayabilir veya parametre işaretçisi (soru işareti '?') kullanabilirsiniz.

> [!NOTE]
> Visual C++ kullanılarak oluşturulan CLR SQL Server depolanan `/clr:safe` yordamlar derleyici seçeneği ile derlenmelidir.

SQL Server için OLE DB sağlayıcısı (SQLOLEDB), depolanan yordamların veri döndürmek için kullandığı aşağıdaki mekanizmaları destekler:

- Yordamdaki her **SELECT** deyimi bir sonuç kümesi oluşturur.

- Yordam, çıktı parametreleri aracılığıyla veri döndürebilir.

- Yordamda bir karşıcı iade kodu olabilir.

> [!NOTE]
> Depolanan yordamları Jet için OLE DB sağlayıcısında kullanamazsınız, çünkü bu sağlayıcı depolanan yordamları desteklemez; yalnızca sorgu dizelerinde sabitlere izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
