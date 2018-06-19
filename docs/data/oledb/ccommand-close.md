---
title: CCommand::Close | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5723c358e0af7cf9b92952bfd843ba90577333e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089770"
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