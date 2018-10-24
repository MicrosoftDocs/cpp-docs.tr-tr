---
title: RCustomRowset devralmayı değiştirme | Microsoft Docs
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
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a6f4827ecf0571878bc0eeaef5dce74326488c61
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990289"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset devralmayı değiştirme

Eklenecek `IRowsetLocate` arabirim basit bir salt okunur sağlayıcı örneği, devralınmasını Değiştir `RCustomRowset`. Başlangıçta `RCustomRowset` devraldığı `CRowsetImpl`. Devralınacak şekilde değiştirmeniz gerekir `CRowsetBaseImpl`.  
  
Bunu yapmak için yeni bir sınıf oluşturun `CMyRowsetImpl`, *özel*RS.h:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// CustomRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>  
{  
...  
};  
```  
  
Şimdi, COM arabirim eşlemesini düzenle *özel*RS.h şu şekilde olacak:  
  
```cpp  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
Bu söyleyen bir COM arabirim eşlemesi oluşturur `CMyRowsetImpl` çağrılacak `QueryInterface` hem `IRowset` ve `IRowsetLocate` arabirimleri. Tüm diğer satır kümesi uygulamasını almak için sınıflar, eşleme bağlantıları `CMyRowsetImpl` sınıfı yeniden `CRowsetBaseImpl` sınıfı OLE DB Şablonları tarafından tanımlı; içindeki COM eşlemesine taramak için OLE DB Şablonları söyler COM_INTERFACE_ENTRY_CHAIN makro eşlemesini kullanır `CRowsetBaseImpl` yanıt olarak bir `QueryInterface` çağırın.  
  
Son olarak, bağlantı `RAgentRowset` için `CMyRowsetBaseImpl` değiştirerek `RAgentRowset` devralınacak `CMyRowsetImpl`gibi:  
  
```cpp  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>  
```  
  
`RAgentRowset` artık `IRowsetLocate` yararlanırken satır kümesi sınıfı için uygulama rest arabirimi.  
  
Bu yapıldığında, yapabilecekleriniz [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)