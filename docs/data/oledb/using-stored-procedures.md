---
title: "Saklı yordamları kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a79ca28b3ae509ef5e493a23222ac76ad2352c9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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