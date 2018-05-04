---
title: CHeapPtrBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ca18054509ab069722e632308b4d8f57706e548
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase sınıfı
Bu sınıfın birkaç akıllı yığın işaretçi sınıfları temelini oluşturur.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Öbek üzerinde depolanması için nesne türü.  
  
 `Allocator`  
 Bellek ayırma kullanacak şekilde sınıfı. Varsayılan olarak, ayırmak ve belleği boşaltmak için CRT yordamlar kullanılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Bellek ayırma için bu yöntemi çağırın.|  
|[CHeapPtrBase::Attach](#attach)|Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|  
|[CHeapPtrBase::Detach](#detach)|Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.|  
|[CHeapPtrBase::Free](#free)|Gösterdiği bir nesneyi silmek için bu yöntemi çağırın bir `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Belleği yeniden tahsis için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|Atama işleci.|  
|[CHeapPtrBase::operator &](#operator_amp)|& İşleci.|  
|[CHeapPtrBase::operator ->](#operator_ptr)|İşaretçi-üye işleci.|  

  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|İşaretçi veri üye değişkeni.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın birkaç akıllı yığın işaretçi sınıfları temelini oluşturur. Türetilen sınıflar için [CHeapPtr](../../atl/reference/cheapptr-class.md) ve [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), kendi oluşturucular ve işleçler ekleyin. Bu sınıfların uygulama örnekleri için bkz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
##  <a name="allocatebytes"></a>  CHeapPtrBase::AllocateBytes  
 Bellek ayırma için bu yöntemi çağırın.  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 Ayrılacak bellek bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek başarılı olduğunda true değerini döndürür ayrılmış, false Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni şu anda işaret var olan bir değerle; diğer bir deyişle, NULL değerine eşit değil.  
  
##  <a name="attach"></a>  CHeapPtrBase::Attach  
 Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pData`  
 `CHeapPtrBase` Nesne sahipliği Bu işaretçinin götürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir `CHeapPtrBase` nesnesini bir işaretçi sahipliğini alır, kapsam dışına çıktığında otomatik olarak işaretçi ve ayrılmış tüm verileri silecektir.  
  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni şu anda işaret var olan bir değerle; diğer bir deyişle, NULL değerine eşit değil.  
  
##  <a name="dtor"></a>  CHeapPtrBase:: ~ CHeapPtrBase  
 Yok Edicisi.  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="detach"></a>  CHeapPtrBase::Detach  
 Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçinin kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi sahipliğini serbest bırakır, ayarlar [CHeapPtrBase::m_pData](#m_pdata) NULL, üye değişkeni ve işaretçiyi kopyasını döndürür.  
  
##  <a name="free"></a>  CHeapPtrBase::Free  
 Gösterdiği bir nesneyi silmek için bu yöntemi çağırın bir `CHeapPtrBase`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından için nesne işaret `CHeapPtrBase` serbest bırakılmaz ve [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni NULL olarak ayarlanır.  
  
##  <a name="m_pdata"></a>  CHeapPtrBase::m_pData  
 İşaretçi veri üye değişkeni.  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye değişkeni işaretçi bilgileri tutar.  
  
##  <a name="operator_amp"></a>  CHeapPtrBase::operator &amp;  
 & İşleci.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösterdiği nesne adresini döndürür `CHeapPtrBase` nesnesi.  
  

##  <a name="operator_ptr"></a>  CHeapPtrBase::operator-&gt;  

 İşaretçi-üye işleci.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değerini döndürür [CHeapPtrBase::m_pData](#m_pdata) üye değişkeni.  
  
### <a name="remarks"></a>Açıklamalar  
 Gösterdiği bir sınıftaki bir yöntemi çağırmak için bu işleci kullanın `CHeapPtrBase` nesnesi. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `CHeapPtrBase` işaret NULL.  
  
##  <a name="operator_t_star"></a>  CHeapPtrBase::operator T *  
 Atama işleci.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür [CHeapPtrBase::m_pData](#m_pdata).  
  
##  <a name="reallocatebytes"></a>  CHeapPtrBase::ReallocateBytes  
 Belleği yeniden tahsis için bu yöntemi çağırın.  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 Yeni bayt cinsinden ayrılacak bellek miktarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bellek başarılı olduğunda true değerini döndürür ayrılmış, false Aksi takdirde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
