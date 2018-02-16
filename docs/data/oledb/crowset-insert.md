---
title: CRowset::INSERT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.Insert
- CRowset.Insert
- CRowset<TAccessor>.Insert
- CRowset<TAccessor>::Insert
- ATL::CRowset<TAccessor>::Insert
- ATL.CRowset.Insert
- CRowset::Insert
- ATL::CRowset::Insert
dev_langs:
- C++
helpviewer_keywords:
- Insert method
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d23396664788f6509b64f9aae88eb9674586fbf
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetinsert"></a>CRowset::Insert
Oluşturur ve erişimci verilerini kullanarak yeni bir satır başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Insert(int nAccessor = 0,   
   bool bGetHRow = false) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nAccessor`  
 [in] Veri eklemek için kullanılacak erişimcisi sayısı.  
  
 *bGetHRow*  
 [in] Eklenen satırın tanıtıcı alınan olup olmadığını gösterir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem isteğe bağlı bir arabirim gerektirir `IRowsetChange`, hangi desteklenmeyebilir tüm sağlayıcılarının; bu durumda, yöntem **E_NOINTERFACE**. De ayarlamalısınız **DBPROP_IRowsetChange** için `VARIANT_TRUE` çağırmadan önce **açık** tablodaki veya satır kümesi içeren komutu.  
  
 Bir veya daha fazla sütun yoksa yazılabilir ekleme başarısız olabilir. Bu sorunu gidermek için imleç haritanızı değiştirin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir satır kümesi ile bir veri kaynağına erişmek ve bu satır kümesinde bir tablo kullanarak bir dize eklemek gösterilmiştir.  
  
 İlk olarak bir tablo sınıfı projenize yeni bir ATL nesnesi ekleyerek oluşturun. Örneğin, çalışma alanı bölmesinde projesine sağ tıklatın ve **yeni ATL nesnesi**. Gelen **veri erişimi** kategorisi, select **tüketici**. Tür bir tüketici nesne oluşturma **tablo**. (Seçme **tablo** doğrudan tablosundan satır oluşturur; seçme **komutu** bir SQL komutu aracılığıyla bir satır kümesi oluşturur.) Bu veri kaynağına erişmek için bir tabloda belirterek bir veri kaynağı seçin. Tüketici nesnenizin çağırırsanız **CCustomerTable**, ekleme kodunuz gibi sonra uygulamak:  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/cpp/crowset-insert_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowset Sınıfı](../../data/oledb/crowset-class.md)