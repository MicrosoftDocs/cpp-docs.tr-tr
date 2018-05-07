---
title: Saklı yordamları kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e5b49daa44fc8c88316134915945ad7ee01bb81a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-stored-procedures"></a>Saklı Yordamları Kullanma
Saklı yordam, veritabanında depolanan yürütülebilir bir nesnedir. Saklı yordam çağırma SQL komutunu çağırmaya benzerdir. (Yerine, çalıştırmak veya istemci uygulaması deyiminde hazırlama) veri kaynağında depolanan yordamları kullanarak, daha yüksek performans, azaltılmış ağ yükünü ve geliştirilmiş tutarlılık ve doğruluk dahil olmak üzere çeşitli avantajları sağlayabilir.  
  
 Saklı yordam (sıfır dahil), herhangi bir sayı olabilir giriş veya çıkış parametrelerini ve dönüş değeri geçirebilirsiniz. Belirli veri değerleri veya parametre işaretçisi kullanın ya da sabit kod parametre değerlerini kullanabilirsiniz (bir soru işareti '?').  
  
> [!NOTE]
>  Visual C++ kullanılarak oluşturulan saklı yordamlar derlenmelidir CLR SQL Server **/CLR: safe** derleyici seçeneği.  
  
 OLE DB sağlayıcısının SQL Server (SQLOLEDB) için saklı yordamlar kullanım verileri döndürmek için aşağıdaki mekanizmayı destekler:  
  
-   Yordam her SELECT deyiminde bir sonuç kümesi oluşturur.  
  
-   Yordam çıkış parametreleri üzerinden veri döndürebilir.  
  
-   Yordamı dönüş kodu bir tamsayı olabilir.  
  
> [!NOTE]
>  Bu sağlayıcı saklı yordamları desteklemediğinden Jet için OLE DB sağlayıcısıyla saklı yordamları kullanamazsınız; yalnızca sabitleri sorgu dizelerine izin verilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)