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
ms.openlocfilehash: a7e97781d245e236c57942db15d61080d6418cfa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209280"
---
# <a name="using-stored-procedures"></a>Saklı Yordamları Kullanma

Saklı yordam, veritabanında depolanan yürütülebilir bir nesnedir. Saklı yordamın çağrılması, SQL komutunu çağırmaya benzerdir. Veri kaynağında saklı yordamları kullanmak (istemci uygulamasında bir deyimin yürütülmesi veya hazırlanması yerine), daha yüksek performans, azaltılmış ağ yükü ve geliştirilmiş tutarlılık ve doğruluk gibi çeşitli avantajlar sağlayabilir.

Saklı yordam herhangi bir sayıda (sıfır dahil) giriş veya çıkış parametresi içerebilir ve bir dönüş değeri geçirebilir. Parametre değerlerini belirli veri değerleri olarak sabit kodya da bir parametre işaretleyicisi (soru işareti '? ') kullanabilirsiniz.

> [!NOTE]
>  Visual C++ kullanılarak oluşturulan, CLR SQL Server saklı yordamların `/clr:safe` derleyici seçeneğiyle derlenmesi gerekir.

SQL Server (SQLOLEDB) için OLE DB sağlayıcısı, saklı yordamların verileri döndürmek için kullandığı aşağıdaki mekanizmaları destekler:

- Yordamdaki her **Select** ifadesiyle bir sonuç kümesi oluşturulur.

- Yordam, çıkış parametreleri aracılığıyla veri döndürebilir.

- Yordam bir tamsayı dönüş koduna sahip olabilir.

> [!NOTE]
> Bu sağlayıcı saklı yordamları desteklemediğinden, Jet için OLE DB sağlayıcısı ile saklı yordamları kullanamazsınız; sorgu dizelerinde yalnızca sabitlere izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
