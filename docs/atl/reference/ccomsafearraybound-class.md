---
title: "CComSafeArrayBound sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4de823b4cdb2d7926b2a9d640b2e8f7352e389fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound sınıfı
Bu sınıf için sarmalayıcı, bir [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d) yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|Oluşturucu.|  
|[GetCount](#getcount)|Öğe sayısını döndürmek için bu yöntemi çağırın.|  
|[GetLowerBound](#getlowerbound)|Alt sınır döndürmek için bu yöntemi çağırın.|  
|[GetUpperBound](#getupperbound)|Üst sınır döndürmek için bu yöntemi çağırın.|  
|[SetCount](#setcount)|Öğe sayısını ayarlamak için bu yöntemi çağırın.|  
|[SetLowerBound](#setlowerbound)|Alt sınır ayarlamak için bu yöntemi çağırın.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#operator_eq)|Ayarlar `CComSafeArrayBound` yeni bir değer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf için sarmalayıcı, **SAFEARRAYBOUND** tarafından kullanılan yapısı [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Sorgulamak ve tek bir boyut üst ve alt sınırları ayarlamak için yöntemler sağlar bir `CComSafeArray` nesne ve içerdiği öğe sayısı. Bir çok boyutlu `CComSafeArray` nesnesini kullanan bir dizi `CComSafeArrayBound` nesneleri, her boyut için bir. Bu nedenle, yöntemleri gibi kullanırken [GetCount](#getcount), bu yöntem öğeleri toplam sayısı çok boyutlu bir diziye döndürmeyecektir unutmayın.  
  
 **Başlık:** atlsafe.h  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsafe.h  
  
##  <a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound  
 Oluşturucu.  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ulCount`  
 Dizideki öğelerin sayısı  
  
 `lLowerBound`  
 Dizi numaralı alt sınır.  
  
### <a name="remarks"></a>Açıklamalar  
 Visual C++ programdan erişilecek diziyse, alt sınırı 0 olarak tanımlanmış olması önerilir. Visual Basic gibi diğer dilleri ile kullanılacak dizi olması durumunda farklı alt sınır değeri kullanmayı tercih edilebilir.  
  
##  <a name="getcount"></a>CComSafeArrayBound::GetCount  
 Öğe sayısını döndürmek için bu yöntemi çağırın.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa ilişkili `CComSafeArray` nesnesi boyutlu bir diziye temsil eder, bu yöntem yalnızca en sağdaki boyutu toplam öğe sayısını döndürür. Kullanım [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) öğeleri toplam sayısı alınamadı.  
  
##  <a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound  
 Alt sınır döndürmek için bu yöntemi çağırın.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alt sınır değeri döndürür `CComSafeArrayBound` nesnesi.  
  
##  <a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound  
 Üst sınır döndürmek için bu yöntemi çağırın.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst sınırının döndürür `CComSafeArrayBound` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üst sınır öğeleri ve alt sınır değeri sayısına bağlıdır. Örneğin, alt sınırı 0'dır ve öğelerin sayısı 10 ise, üst sınırı otomatik olarak 9'a ayarlanır.  
  
##  <a name="operator_eq"></a>CComSafeArrayBound::operator =  
 Ayarlar `CComSafeArrayBound` yeni bir değer.  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `bound`  
 A `CComSafeArrayBound` nesnesi.  
  
 `ulCount`  
 Öğe sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `CComSafeArrayBound` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CComSafeArrayBound` Nesne var olan kullanarak atanabilir `CComSafeArrayBound`, ya da sağlayarak, durumu alt sınırı 0 olarak ayarlanmış varsayılan olarak öğe sayısı.  
  
##  <a name="setcount"></a>CComSafeArrayBound::SetCount  
 Öğe sayısını ayarlamak için bu yöntemi çağırın.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `ulCount`  
 Öğe sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğelerin sayısını döndürür `CComSafeArrayBound` nesnesi.  
  
##  <a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound  
 Alt sınır ayarlamak için bu yöntemi çağırın.  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `lLowerBound`  
 Alt sınır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni alt sınır değeri döndürür `CComSafeArrayBound` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Visual C++ programdan erişilecek diziyse, alt sınırı 0 olarak tanımlanmış olması önerilir. Visual Basic gibi diğer dilleri ile kullanılacak dizi olması durumunda farklı alt sınır değeri kullanmayı tercih edilebilir.  
  
 Üst sınır öğeleri ve alt sınır değeri sayısına bağlıdır. Örneğin, alt sınırı 0'dır ve öğelerin sayısı 10 ise, üst sınırı otomatik olarak 9'a ayarlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
