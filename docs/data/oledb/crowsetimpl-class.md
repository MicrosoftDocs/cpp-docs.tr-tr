---
title: "CRowsetImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
dev_langs: C++
helpviewer_keywords: CRowsetImpl class
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2390a474e289ea41fd676759d12b92e8a22e462a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetimpl-class"></a>CRowsetImpl Sınıfı
Birçok uygulama arabirimlerinin birden çok devralma gerektirmeden standart bir OLE DB satır kümesi uygulaması sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl < T, IRowset >   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öğesinden türetilen kullanıcının sınıf `CRowsetImpl`.  
  
 `Storage`  
 Kullanıcı kayıt sınıfı.  
  
 `CreatorClass`  
 Satır kümesi özelliklerini içeren sınıf; genellikle komutu.  
  
 `ArrayType`  
 Satır kümesinin verileri için depolama görecek sınıfı. Bu parametre için varsayılan olarak `CAtlArray`, ancak gerekli işlevselliğini destekleyen herhangi bir sınıf olabilir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Namefromdbıd](../../data/oledb/crowsetimpl-namefromdbid.md)|Bir dizeden ayıklar bir **DBID** ve kendisine kopyalar `bstr` geçirildi.|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|Doğrular ve depolar **DBID**iki dizeyi s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|  
  
### <a name="overridable-methods"></a>Geçersiz kılınabilir yöntemleri  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|Belirli bir istemci isteği için sütun bilgileri alır.|  
|[Getcommandfromıd](../../data/oledb/crowsetimpl-getcommandfromid.md)|Biri veya her ikisi parametreleri dize değerlerini içeriyorsa ve bu durumda, bakar kopyalar dize değerleri veri üyelerine [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|Her iki bakın veya her ikisini de denetler **DBID**s dize değerleri içeren ve varsa, bunları kendi veri üyelerine kopyalar [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|Varsayılan olarak, bir `CAtlArray` kullanıcı kayıt şablonu bağımsız değişkeni üzerinde templatizes `CRowsetImpl`. Başka bir dizi türü sınıfı değiştirerek kullanılabilir `ArrayType` şablon bağımsız değişken `CRowsetImpl`.|  
|[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|Satır kümesinin ilk komut içerir.|  
|[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|Satır kümesinin başlangıç dizini içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CRowsetImpl`geçersiz kılmaları statik upcasts biçiminde sağlar. Yöntemleri verilen satır komut metni doğrulayacak şekilde denetler. Kendi oluşturabilirsiniz `CRowsetImpl`-birden çok devralınan uygulama arabirimlerinizi yaparak sınıfı stili. Kendisi için sağlamanız gerekir uygulamasıdır tek yöntem **yürütme**. Ne tür bir satır kümesi oluşturmakta olduğunuz bağlı olarak, creator yöntemi için farklı imzalar beklediği **yürütme**. Kullanıyorsanız, örneğin, bir `CRowsetImpl`-türetilmiş bir şema satır kümesi uygulamak için sınıf **yürütme** yöntemi, aşağıdaki imzası olacaktır:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 Oluşturuyorsanız, bir `CRowsetImpl`-türetilmiş bir komutu veya oturumun satır kümesi, uygulamak için sınıf **yürütme** yöntemi, aşağıdaki imzası olacaktır:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Herhangi bir uygulamak için `CRowsetImpl`-türetilen **yürütme** yöntemleri, iç veri arabelleklerinin doldurmanız gerekir ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h