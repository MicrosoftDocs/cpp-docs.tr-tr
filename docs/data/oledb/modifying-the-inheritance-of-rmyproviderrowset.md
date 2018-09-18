---
title: RMyProviderRowset devralmayı değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 77b26d1d0b67726e1ba2cd66d0e181bc04105a6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028174"
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>RMyProviderRowset Devralmayı Değiştirme

Eklenecek `IRowsetLocate` arabirim basit bir salt okunur sağlayıcı örneği, devralınmasını Değiştir `RMyProviderRowset`. Başlangıçta `RMyProviderRowset` devraldığı `CRowsetImpl`. Devralınacak şekilde değiştirmeniz gerekir `CRowsetBaseImpl`.  
  
Bunu yapmak için yeni bir sınıf oluşturun `CMyRowsetImpl`, MyProviderRS.h:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>  
{  
...  
};  
```  
  
Şimdi, şöyle MyProviderRS.h COM arabirim eşlemesini düzenle:  
  
```cpp  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
Bu söyleyen bir COM arabirim eşlemesi oluşturur `CMyRowsetImpl` çağrılacak `QueryInterface` hem `IRowset` ve `IRowsetLocate` arabirimleri. Tüm diğer satır kümesi uygulamasını almak için sınıflar, eşleme bağlantıları `CMyRowsetImpl` sınıfı yeniden `CRowsetBaseImpl` sınıfı OLE DB Şablonları tarafından tanımlı; içindeki COM eşlemesine taramak için OLE DB Şablonları söyler COM_INTERFACE_ENTRY_CHAIN makro eşlemesini kullanır `CRowsetBaseImpl` yanıt olarak bir `QueryInterface` çağırın.  
  
Son olarak, bağlantı `RAgentRowset` için `CMyRowsetBaseImpl` değiştirerek `RAgentRowset` devralınacak `CMyRowsetImpl`gibi:  
  
```cpp  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
`RAgentRowset` artık `IRowsetLocate` yararlanırken satır kümesi sınıfı için uygulama rest arabirimi.  
  
Bu yapıldığında, yapabilecekleriniz [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)