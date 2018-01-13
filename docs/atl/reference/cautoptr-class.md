---
title: "CAutoPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
dev_langs: C++
helpviewer_keywords: CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b8ded7bbf4dbe4e4f2ada7054cebab996934316
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cautoptr-class"></a>CAutoPtr sınıfı
Bu sınıf, bir akıllı işaretçi nesneyi temsil eder.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İşaretçi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|Oluşturucu.|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.|  
|[CAutoPtr::Detach](#detach)|Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.|  
|[CAutoPtr::Free](#free)|Gösterdiği bir nesneyi silmek için bu yöntemi çağırın bir `CAutoPtr`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|Atama işleci.|  
|[CAutoPtr::operator =](#operator_eq)|Atama işleci.|  
|[CAutoPtr::operator ->](#operator_ptr)|İşaretçi-üye işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|İşaretçi veri üye değişkeni.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf oluşturmak ve kapsamının dışına düştüğünde otomatik olarak kaynak kullanımını azaltarak bellek sızıntıları karşı korunmasına yardımcı olacak bir akıllı işaretçi yönetmek için yöntemler sağlar.  
  
 Ayrıca `CAutoPtr`kullanıcının kopya Oluşturucu atama işleci aktarımı sahipliği işaretçisinin kaynak işaretçi hedef işaretçiyi kopyalama ve kaynak işaretçisi NULL olarak ayarlamak. Bu nedenle iki olmasını imkansız `CAutoPtr` her aynı işaretçi depolama nesneleri ve bu aynı işaretçi iki kez silme olasılığını azaltır.  
  
 `CAutoPtr`Ayrıca işaretçileri koleksiyonları oluşturulmasını basitleştirir. Koleksiyon sınıfı türetme ve yıkıcı geçersiz kılma yerine koleksiyonu yapmak daha basit `CAutoPtr` nesneleri. Koleksiyon silindiğinde, `CAutoPtr` nesne kapsam dışında gidin ve otomatik olarak kendilerini silin.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) ve çeşitleri iş aynı şekilde `CAutoPtr`ayırma ve serbest farklı heap işlevleri yerine C++ kullanarak bellek dışında **yeni** ve **silme** işleçler. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) benzer `CAutoPtr`, onu kullanır tek fark **vektör new []** ve **vektör silme []** ayırmak ve belleği boşaltmak için.  
  
 Ayrıca bkz. [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) ve [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) zaman diziler veya akıllı işaretçiler listesi gereklidir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>CAutoPtr::Attach  
 Varolan bir işaretçi sahipliğini almak için bu yöntemi çağırın.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 `CAutoPtr` Nesne sahipliği Bu işaretçinin götürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman bir `CAutoPtr` nesnesini bir işaretçi sahipliğini alır, kapsam dışına çıktığında otomatik olarak işaretçi ve ayrılmış tüm verileri silecektir. Varsa [CAutoPtr::Detach](#detach) olduğu adlı Programcı yeniden herhangi boşaltma sorumluluğunu verilen kaynakları tahsis edilir.  
  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır [CAutoPtr::m_p](#m_p) veri üyesi için var olan bir değer şu anda işaret; diğer bir deyişle, NULL değerine eşit değil.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).  
  
##  <a name="cautoptr"></a>CAutoPtr::CAutoPtr  
 Oluşturucu.  
  
```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<> 
CAutoPtr(CAutoPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Varolan bir işaretçi.  
  
 `TSrc`  
 Bir başkası tarafından yönetilen türü `CAutoPtr`, geçerli nesneyi başlatmak için kullanılan.  
  
### <a name="remarks"></a>Açıklamalar  
 `CAutoPtr` Nesne var olan bir işaretçi kullanılarak oluşturulabilir, bu durumda işaretçinin sahipliğini aktarır.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).  
  
##  <a name="dtor"></a>CAutoPtr:: ~ CAutoPtr  
 Yok Edicisi.  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır. Çağrıları [CAutoPtr::Free](#free).  
  
##  <a name="detach"></a>CAutoPtr::Detach  
 Bir işaretçi sahipliğini serbest bırakmak için bu yöntemi çağırın.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçinin kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi sahipliğini serbest bırakır, ayarlar [CAutoPtr::m_p](#m_p) veri üye değişkeni null ve işaretçiyi kopyasını döndürür. Çağırdıktan sonra **ayırma**, bunu herhangi boşaltmak için programcı kadar kaynaklar ayrıldığı `CAutoPtr` nesnesi önceden kabul reponsibility.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).  
  
##  <a name="free"></a>CAutoPtr::Free  
 Gösterdiği bir nesneyi silmek için bu yöntemi çağırın bir `CAutoPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından için nesne işaret `CAutoPtr` serbest bırakılmaz ve [CAutoPtr::m_p](#m_p) veri üye değişkeni NULL olarak ayarlanır.  
  
##  <a name="m_p"></a>CAutoPtr::m_p  
 İşaretçi veri üye değişkeni.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye değişkeni işaretçi bilgileri tutar.  
  
##  <a name="operator_eq"></a>CAutoPtr::operator =  
 Atama işleci.  
  
```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bir işaretçi.  
  
 `TSrc`  
 Sınıf türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru döndürür bir **CAutoPtr\< T >**.  
  
### <a name="remarks"></a>Açıklamalar  
 Atama işleci ayırır `CAutoPtr` geçerli bir işaretçi bir nesneden ve yeni işaretçi ekler `p`, onun yerine.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_ptr"></a>CAutoPtr::operator-&gt;  
 İşaretçi-üye işleci.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değerini döndürür [CAutoPtr::m_p](#m_p) veri üye değişkeni.  
  
### <a name="remarks"></a>Açıklamalar  
 Gösterdiği bir sınıftaki bir yöntemi çağırmak için bu işleci kullanın `CAutoPtr` nesnesi. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `CAutoPtr` işaret NULL.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_t_star"></a>CAutoPtr::operator T *  
 Atama işleci.  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınıf şablonunda tanımlanan nesne veri türü için bir işaretçi döndürür.  
  
### <a name="example"></a>Örnek  
 Örnekte bkz [CAutoPtr genel bakış](../../atl/reference/cautoptr-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr sınıfı](../../atl/reference/cautovectorptr-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
