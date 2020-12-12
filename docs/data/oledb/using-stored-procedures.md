---
description: 'Hakkında daha fazla bilgi edinin: saklı yordamları kullanma'
title: Saklı Yordamları Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
ms.openlocfilehash: 6bd7dbd3980eb4bfe0fbca71d86af080128d3309
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319111"
---
# <a name="using-stored-procedures"></a>Saklı Yordamları Kullanma

Saklı yordam, veritabanında depolanan yürütülebilir bir nesnedir. Saklı yordamın çağrılması, SQL komutunu çağırmaya benzerdir. Veri kaynağında saklı yordamları kullanmak (istemci uygulamasında bir deyimin yürütülmesi veya hazırlanması yerine), daha yüksek performans, azaltılmış ağ yükü ve geliştirilmiş tutarlılık ve doğruluk gibi çeşitli avantajlar sağlayabilir.

Saklı yordam herhangi bir sayıda (sıfır dahil) giriş veya çıkış parametresi içerebilir ve bir dönüş değeri geçirebilir. Parametre değerlerini belirli veri değerleri olarak sabit kodya da bir parametre işaretleyicisi (soru işareti '? ') kullanabilirsiniz.

> [!NOTE]
> CLR SQL Server Visual C++ kullanılarak oluşturulan saklı yordamların `/clr:safe` derleyici seçeneğiyle derlenmesi gerekir.

SQL Server (SQLOLEDB) için OLE DB sağlayıcısı, saklı yordamların verileri döndürmek için kullandığı aşağıdaki mekanizmaları destekler:

- Yordamdaki her **Select** ifadesiyle bir sonuç kümesi oluşturulur.

- Yordam, çıkış parametreleri aracılığıyla veri döndürebilir.

- Yordam bir tamsayı dönüş koduna sahip olabilir.

> [!NOTE]
> Bu sağlayıcı saklı yordamları desteklemediğinden, Jet için OLE DB sağlayıcısı ile saklı yordamları kullanamazsınız; sorgu dizelerinde yalnızca sabitlere izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
