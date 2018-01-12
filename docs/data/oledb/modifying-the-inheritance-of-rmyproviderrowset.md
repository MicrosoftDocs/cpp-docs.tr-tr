---
title: "RMyProviderRowset devralmayı değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ff6e953bf706e0e8767fe6f97fe1d31b70431d08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>RMyProviderRowset Devralmayı Değiştirme
Eklemek için `IRowsetLocate` arabirim basit salt okunur sağlayıcı örneği, devralma Değiştir **RMyProviderRowset**. Başlangıçta, **RMyProviderRowset** devraldığı `CRowsetImpl`. Devralınan şekilde değiştirmenize gerek **CRowsetBaseImpl**.  
  
 Bunu yapmak için yeni bir sınıf oluşturun `CMyRowsetImpl`, MyProviderRS.h:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate > >  
{  
...  
};  
```  
  
 Şimdi, COM arabirimi eşlemesini şöyle MyProviderRS.h düzenleyin:  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Bu söyleyen bir COM arabirimi eşlemesini oluşturur `CMyRowsetImpl` çağırmak için **QueryInterface** her ikisi için de `IRowset` ve `IRowsetLocate` arabirimleri. Tüm diğer satır kümesi için uygulama almak için sınıflar, eşleme bağlantıları `CMyRowsetImpl` sınıfı başa **CRowsetBaseImpl** sınıf OLE DB Şablonları tarafından tanımlanan; harita söyler COM_INTERFACE_ENTRY_CHAIN makrosu kullanır COM taramak için OLE DB Şablonları eşleme **CRowsetBaseImpl** yanıt olarak bir `QueryInterface` çağırın.  
  
 Son olarak, bağlantı `RAgentRowset` için `CMyRowsetBaseImpl` değiştirerek `RAgentRowset` devralınacak `CMyRowsetImpl`aşağıdaki gibi:  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset`artık kullanabilirsiniz `IRowsetLocate` satır kümesi sınıfı için uygulama kalan yararlanarak sırasında arabirimi.  
  
 Bu yapıldığında, yapabilecekleriniz [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)