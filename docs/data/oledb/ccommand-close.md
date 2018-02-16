---
title: CCommand::Close | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 10d3ce633add0dea4a3b9a79a32fd380761b5a2f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ccommandclose"></a>CCommand::Close
Komutla ilişkili erişimcisi satır serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
void Close();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir komut bir satır kümesi, sonuç set erişimcisi ve (isteğe bağlı) bir parametre erişimcisi (aksine, parametreleri desteklemez ve bir parametre erişimcisi gerekmez tablolar) kullanır.  
  
 Bir komut yürüttüğünüzde her ikisi de çağırmalıdır `Close` ve [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) sonra komutu.  
  
 Aynı komutu tekrar tekrar çalıştırmak istediğinizde, çağırarak her sonuç set erişimcisi serbest bırakmalısınız `Close` çağırmadan önce `Execute`. Seri sonunda, parametre erişimcisi çağırarak serbest bırakmalısınız `ReleaseCommand`. Başka bir yaygın bir senaryo çıktı parametreleri olan bir saklı yordamı çağırma. Sonuç kümesi erişimcisi kapatana kadar birçok sağlayıcıları (örneğin, SQL Server için OLE DB sağlayıcısı) çıkış parametresi değerlerini erişilemeyecek. Çağrı `Close` döndürülen satır kümesi ve sonuç set erişimcisi, ancak parametre erişimcisi kapatmak için böylece çıkış parametresi değerlerini almanıza olanak sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, nasıl çağırabilirsiniz gösterir `Close` ve `ReleaseCommand` çalıştırdığınızda aynı komutu tekrar tekrar.  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommand sınıfı](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)