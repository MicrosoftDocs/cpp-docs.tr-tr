---
title: CArrayRowset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b7975c91631df24ab12858677a770c38dc0f6411
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338918"
---
# <a name="carrayrowset-class"></a>CArrayRowset Sınıfı
Dizi söz dizimini kullanarak bir satır öğeleri erişir.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template < class TAccessor >  
class CArrayRowset : 
   public CVirtualBuffer <TAccessor>, 
   protected CBulkRowset <TAccessor>  
```  
  
### <a name="parameters"></a>Parametreler  
 *TAccessor*  
 Satır kümesi kullanmak istediğiniz erişimci sınıfında türü.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CArrayRowset](#carrayrowset)|Oluşturucu.|  
|[Anlık Görüntü](#snapshot)|Tüm satır kümesi belleğe okur.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleci&#91;&#93;](#operator)|Bir öğe kümesi erişir.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](#nrowsread)|Zaten okunan satır sayısı.|  
  
## <a name="carrayrowset"></a> CArrayRowset::CArrayRowset
Yeni bir oluşturur `CArrayRowset` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
CArrayRowset(int nMax = 100000);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *nMax*  
 [in] Satır kümesinde satır sayısı. 

## <a name="snapshot"></a> CArrayRowset::Snapshot
Tüm satır kümesi, bir resim veya bunu anlık görüntü oluşturma belleğe okur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Snapshot() throw();  
```  

## <a name="operator"></a> CArrayRowset::operator
Bir satır kümesinde erişmek için dizi benzeri sözdizimi sağlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
TAccessor & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *TAccessor*  
 Bir şablonlu parametresi kümesi içinde depolanan erişimcisinin türünü belirtir.  
  
 *nRow*  
 [in] Erişmek istediğiniz satır (dizi öğesi) sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstenen satır içeriği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *nRow* satır kümesinde satır sayısını aşıyor, bir özel durum oluşturulur.  

## <a name="nrowsread"></a> CArrayRowset::m_nRowsRead
Zaten okunmuş satır kümesinde satır sayısını içerir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
ULONG m_nRowsRead;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset Sınıfı](../../data/oledb/crowset-class.md)