---
title: "CComGITPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
dev_langs: C++
helpviewer_keywords: CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c001d0d1ca8e756b24d97051d100e7d71723569c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomgitptr-class"></a>CComGITPtr sınıfı
Bu sınıf, arabirim işaretçileri ilgilenmek için yöntemleri ve genel arabirim tablosu (GIT) sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class CComGITPtr
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 GIT içinde depolanması için arabirim işaretçisi türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Oluşturucu.|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|Arabirim işaretçisi genel arabirim tablosu (GIT) kaydetmek için bu yöntemi çağırın.|  
|[CComGITPtr::CopyTo](#copyto)|Arabirim geçirilen işaretçisine (GIT) genel arabirim tablosundan kopyalamak için bu yöntemi çağırın.|  
|[CComGITPtr::Detach](#detach)|Arabirimden ilişkisini kaldırmak için bu yöntemi çağırın `CComGITPtr` nesnesi.|  
|[CComGITPtr::GetCookie](#getcookie)|Tanımlama bilgisinden döndürmek için bu yöntemi çağırabilmeniz `CComGITPtr` nesnesi.|  
|[CComGITPtr::Revoke](#revoke)|Arabirim (GIT) genel arabirim tablodan kaldırmak için bu yöntemi çağırın.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](#operator_dword)|Tanımlama bilgisinden döndürür `CComGITPtr` nesnesi.|  
|[CComGITPtr::operator =](#operator_eq)|Atama işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Tanımlama bilgisi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ücretsiz iş parçacıklı Sıralayıcı toplamak ve diğer nesneleri elde arabirim işaretçileri kullanmak gereken nesneleri arabirimler doğru şekilde sıralanmış emin olmak için ek adımlar atmanız gerekir. Genellikle bu arabirim işaretçileri GIT depolamak ve işaretçiyi GIT her kullanılışında alma içerir. Sınıf `CComGITPtr` GIT içinde depolanan arabirim işaretçileri kullanmanıza yardımcı olması için sağlanmıştır.  
  
> [!NOTE]
>  Genel arabirim tablo tesis yalnızca DCOM sürüm 1.1 ile Windows 95 ve daha sonra Windows 98, Windows NT 4.0 Service Pack 3 ve üzeri ve Windows 2000 üzerinde kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="attach"></a>CComGITPtr::Attach  
 Arabirim işaretçisi genel arabirim tablosu (GIT) kaydetmek için bu yöntemi çağırın.  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 GIT eklenecek arabirimi işaretçisi.  
  
 `dwCookie`  
 Arabirim işaretçisi tanımlamak için kullanılan tanımlama bilgisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, GIT geçerli değilse veya tanımlama bilgisi NULL değerine eşit olup olmadığını onaylama hata meydana gelir.  
  
##  <a name="ccomgitptr"></a>CComGITPtr::CComGITPtr  
 Oluşturucu.  
  
```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`p`  
 Genel arabirim tablosu (GIT) depolanması için bir arabirim işaretçisi.  
  
 [in]`git`  
 Var olan bir başvuru `CComGITPtr` nesnesi.  
  
 [in]`dwCookie`  
 Arabirim işaretçisi tanımlamak için kullanılan bir tanımlama bilgisi.  
  
 [in]`rv`  
 Kaynak `CComGITPtr` verileri taşımak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir `CComGITPtr` nesnesi, isteğe bağlı olarak var olan kullanarak `CComGITPtr` nesnesi.  
  
 Oluşturucu kullanılarak `rv` bir taşıma oluşturucusuna değil. Veri kaynağından taşınır `rv`ve ardından `rv` temizlenir.  
  
##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr  
 Yok Edicisi.  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim (GIT), genel arabirim tablodan kaldırır kullanarak [CComGITPtr::Revoke](#revoke).  
  
##  <a name="copyto"></a>CComGITPtr::CopyTo  
 Arabirim geçirilen işaretçisine (GIT) genel arabirim tablosundan kopyalamak için bu yöntemi çağırın.  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pp`  
 Arabirim alacak işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 GIT arabiriminden geçirilen işaretçiyi kopyalanır. Artık gerekli olmadığında işaretçinin çağıran tarafından serbest bırakılması gerekir.  
  
##  <a name="detach"></a>CComGITPtr::Detach  
 Arabirimden ilişkisini kaldırmak için bu yöntemi çağırın `CComGITPtr` nesnesi.  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanımlama bilgisinden döndürür `CComGITPtr` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim GIT kaldırmak için arayan kadar olan kullanarak [CComGITPtr::Revoke](#revoke).  
  
##  <a name="getcookie"></a>CComGITPtr::GetCookie  
 Tanımlama bilgisinden döndürmek için bu yöntemi çağırabilmeniz `CComGITPtr` nesnesi.  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanımlama bilgisini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tanımlama bilgisinin bir arabirim ve konumunu tanımlamak için kullanılan bir değişkendir.  
  
##  <a name="m_dwcookie"></a>CComGITPtr::m_dwCookie  
 Tanımlama bilgisi.  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tanımlama bilgisi, bir arabirim ve konumunu tanımlamak için kullanılan bir üye değişkendir.  
  
##  <a name="operator_eq"></a>CComGITPtr::operator =  
 Atama işleci.  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`p`  
 Bir arabirim için bir işaretçi.  
  
 [in]`git`  
 Bir başvuru bir `CComGITPtr` nesnesi.  
  
 [in]`dwCookie`  
 Arabirim işaretçisi tanımlamak için kullanılan bir tanımlama bilgisi.  
  
 [in]`rv`  
 `CComGITPtr` Verileri taşımak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CComGITPtr` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir değer atayan bir `CComGITPtr` nesnesi, varolan bir nesneyi veya bir genel arabirim tablo referansı.  
  
##  <a name="operator_dword"></a>CComGITPtr::operator DWORD  
 İle ilişkili tanımlama bilgisi döndürür `CComGITPtr` nesnesi.  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tanımlama bilgisinin bir arabirim ve konumunu tanımlamak için kullanılan bir değişkendir.  
  
##  <a name="revoke"></a>CComGITPtr::Revoke  
 Geçerli arabirimi (GIT) genel arabirim tablodan kaldırmak için bu yöntemi çağırın.  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Arabirim GIT kaldırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ücretsiz iş parçacıklı Sıralayıcı](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Arabirimleri grupların erişme](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [Genel arabirim tablosu kullanma zamanı](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
