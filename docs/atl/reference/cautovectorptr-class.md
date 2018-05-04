---
title: CAutoVectorPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df21eabe70c1d9ed8684fa1409e24dcdc76ffec0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr sınıfı
Bu sınıf vektör kullanarak yeni bir akıllı işaretçi nesneyi temsil eder ve delete işleçleri.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CAutoVectorPtr
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İşaretçi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Oluşturucu.|  
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoVectorPtr::Allocate](#allocate)|Gösterdiği nesneler dizisi gerektirdiği bellek ayırmak için bu yöntemi çağırabilmeniz `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](#attach)|Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|  
|[CAutoVectorPtr::Detach](#detach)|Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.|  
|[CAutoVectorPtr::Free](#free)|Gösterdiği bir nesneyi silmek için bu yöntemi çağırın bir `CAutoVectorPtr`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T *](#operator_t__star)|Atama işleci.|  
|[CAutoVectorPtr::operator =](#operator_eq)|Atama işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoVectorPtr::m_p](#m_p)|İşaretçi veri üye değişkeni.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf oluşturmak ve kapsamının dışına düştüğünde otomatik olarak kaynak kullanımını azaltarak bellek sızıntıları karşı korunmasına yardımcı olacak bir akıllı işaretçi yönetmek için yöntemler sağlar. `CAutoVectorPtr` benzer `CAutoPtr`, bu tek fark `CAutoVectorPtr` kullanan [vektör yeni&#91; &#93; ](../../standard-library/new-operators.md#op_new_arr) ve [vektör silme&#91; &#93; ](../../standard-library/new-operators.md#op_delete_arr) ayırmak ve belleği boşaltmak için C++ yerine **yeni** ve **silmek** işleçler. Bkz: [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) , koleksiyon sınıfları `CAutoVectorPtr` gereklidir.  

  
 Bkz: [CAutoPtr](../../atl/reference/cautoptr-class.md) akıllı işaretçi sınıfı kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="allocate"></a>  CAutoVectorPtr::Allocate  
 Gösterdiği nesneler dizisi gerektirdiği bellek ayırmak için bu yöntemi çağırabilmeniz `CAutoVectorPtr`.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nElements`  
 Dizideki öğelerin sayısı  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış bellek başarılı olduğunda true değerini döndürür, başarısız olduğunda false.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır [CAutoVectorPtr::m_p](#m_p) üye değişkeni şu anda işaret var olan bir değerle; diğer bir deyişle, NULL değerine eşit değil.  
  
##  <a name="attach"></a>  CAutoVectorPtr::Attach  
 Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 `CAutoVectorPtr` Nesne sahipliği Bu işaretçinin götürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir `CAutoVectorPtr` nesnesini bir işaretçi sahipliğini alır, kapsam dışına çıktığında otomatik olarak işaretçi ve ayrılmış tüm verileri silecektir. Varsa [CAutoVectorPtr::Detach](#detach) olduğu adlı Programcı yeniden herhangi boşaltma sorumluluğunu verilen kaynakları tahsis edilir.  
  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır [CAutoVectorPtr::m_p](#m_p) üye değişkeni şu anda işaret var olan bir değerle; diğer bir deyişle, NULL değerine eşit değil.  
  
##  <a name="cautovectorptr"></a>  CAutoVectorPtr::CAutoVectorPtr  
 Oluşturucu.  
  
```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Varolan bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CAutoVectorPtr` Nesne var olan bir işaretçi kullanılarak oluşturulabilir, bu durumda işaretçinin sahipliğini aktarır.  
  
##  <a name="dtor"></a>  CAutoVectorPtr:: ~ CAutoVectorPtr  
 Yok Edicisi.  
  
```
~CAutoVectorPtr() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır. Çağrıları [CAutoVectorPtr::Free](#free).  
  
##  <a name="detach"></a>  CAutoVectorPtr::Detach  
 Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçinin kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi sahipliğini serbest bırakır, ayarlar [CAutoVectorPtr::m_p](#m_p) NULL, üye değişkeni ve işaretçiyi kopyasını döndürür. Çağırdıktan sonra **ayırma**, bunu herhangi boşaltmak için programcı kadar kaynaklar ayrıldığı `CAutoVectorPtr` nesnesi önceden kabul sorumluluk.  
  
##  <a name="free"></a>  CAutoVectorPtr::Free  
 Gösterdiği bir nesneyi silmek için bu yöntemi çağırın bir `CAutoVectorPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından için nesne işaret `CAutoVectorPtr` serbest bırakılmaz ve [CAutoVectorPtr::m_p](#m_p) üye değişkeni NULL olarak ayarlanır.  
  
##  <a name="m_p"></a>  CAutoVectorPtr::m_p  
 İşaretçi veri üye değişkeni.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye değişkeni işaretçi bilgileri tutar.  
  
##  <a name="operator_eq"></a>  CAutoVectorPtr::operator =  
 Atama işleci.  
  
```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru döndürür bir **CAutoVectorPtr\< T >**.  
  
### <a name="remarks"></a>Açıklamalar  
 Atama işleci ayırır `CAutoVectorPtr` geçerli bir işaretçi bir nesneden ve yeni işaretçi ekler `p`, onun yerine.  
  
##  <a name="operator_t__star"></a>  CAutoVectorPtr::operator T *  
 Atama işleci.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf şablonunda tanımlanan nesne veri türü için bir işaretçi döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAutoPtr sınıfı](../../atl/reference/cautoptr-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
