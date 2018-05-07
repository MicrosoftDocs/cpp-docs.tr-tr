---
title: CUtlProps::onınterfacerequested | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- OnInterfaceRequested method
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50a1f17294a91446e71a51ffdac6c5aec83f2c9a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cutlpropsoninterfacerequested"></a>CUtlProps::OnInterfaceRequested
Bir tüketici bir yöntem bir nesne oluşturma arabirimleri çağırdığında isteğe bağlı bir arabirim için isteklerini işler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 [in] İstenen arabirim için IID. Daha fazla ayrıntı için açıklamasını görmek `riid` parametresinin `ICommand::Execute` içinde *OLE DB Programcının Başvurusu* (içinde *MDAC SDK*).  
  
## <a name="remarks"></a>Açıklamalar  
 **Onınterfacerequested** bir tüketici bir yöntem bir nesne oluşturma arabirimleri çağırdığında isteğe bağlı bir arabirim için tüketici isteklerini işler (gibi **IDBCreateSession**, **IDBCreateCommand**, `IOpenRowset`, veya `ICommand`). İstenen arabirim için karşılık gelen OLE DB özelliğini ayarlar. Örneğin, tüketici isterse **IID_IRowsetLocate**, **Onınterfacerequested** ayarlar **DBPROP_IRowsetLocate** arabirimi. Bunun yapılması satır kümesi oluşturma sırasında doğru durumda tutar.  
  
 Tüketici çağırdığında bu yöntem çağrılır **IOpenRowset::OpenRowset** veya `ICommand::Execute`.  
  
 Bir tüketici nesneyi açar ve isteğe bağlı bir arabirim isterse sağlayıcı bu arabirimi ile ilişkili özelliği ayarlanmalıdır. `VARIANT_TRUE`. Özellik özgü işlenmesini sağlamak için **Onınterfacerequested** sağlayıcının önce adlı **yürütme** yöntemi çağrılır. Varsayılan olarak, **Onınterfacerequested** aşağıdaki arabirimleri işler:  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 Diğer arabirimleri işlemek istiyorsanız, bu veri kaynağı, oturum, komut veya satır kümesi sınıfı işlem işlevlere işlevinde geçersiz kılar. Geçersiz kılma özellikleri ayarlama, tüm zincirleme özelliklerini de ayarlar emin olmak için normal ayarla/al özellikleri arabirimleri aracılığıyla tamamlamalıdır (bkz [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CUtlProps Sınıfı](../../data/oledb/cutlprops-class.md)