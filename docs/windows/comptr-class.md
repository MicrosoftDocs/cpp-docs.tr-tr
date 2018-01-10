---
title: "ComPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr
dev_langs: C++
helpviewer_keywords: ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04f8181c7308d63cc4fe07aaf4a05d34ccfaf132
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptr-class"></a>ComPtr Sınıfı
Oluşturur bir *akıllı işaretçi* şablon parametresi tarafından belirtilen arabirimi temsil eden tür. ComPtr otomatik olarak bir başvuru sayısı için temel arabirim işaretçisi tutar ve başvuru sayısı sıfır olarak gittiğinde arabirimi serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T  
>  
class ComPtr;  
  
template<  
   class U  
>  
friend class ComPtr;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 ComPtr temsil eden arabirim.  
  
 `U`  
 Geçerli ComPtr bir arkadaş olduğu bir sınıf. (Bu parametre kullandığı şablonunu korunur.)  
  
## <a name="remarks"></a>Açıklamalar  
 ComPtr <> temel arabirim işaretçisi temsil eden bir tür bildirir. ComPtr <> kullanabilir bir değişkeni bildirme ve ardından OK üye erişimi işleci (`->`) bir arabirim üye işlevine erişmek için.  
  
 Akıllı işaretçiler hakkında daha fazla bilgi için "COM akıllı işaretçiler" alt bölümüne bakın [COM kodlama uygulamalarını](http://msdn.microsoft.com/en-us/76aca556-b4d6-4e67-a2a3-4439900f0c39)MSDN Kitaplığı'nda konu.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`InterfaceType`|Bir eş tarafından belirtilen tür için `T` şablon parametresi.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtr::ComPtr Oluşturucusu](../windows/comptr-comptr-constructor.md)|ComPtr sınıfı yeni bir örneğini intializes. Aşırı varsayılan, kopyalama, taşıma ve dönüştürme oluşturucuları sağlar.|  
|[ComPtr::~ComPtr Yıkıcısı](../windows/comptr-tilde-comptr-destructor.md)|ComPtr örneği deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtr::As Metodu](../windows/comptr-as-method.md)|Belirtilen şablon parametresi tarafından tanımlanan arabirimi temsil eden bir ComPtr nesnesi döndürür.|  
|[ComPtr::AsIID Metodu](../windows/comptr-asiid-method.md)|Belirtilen arabirim kimliği ile tanımlanan arabirimi temsil eden bir ComPtr nesnesi döndürür|  
|[ComPtr::AsWeak Metodu](../windows/comptr-asweak-method.md)|Geçerli nesne zayıf bir başvuru alır.|  
|[ComPtr::Attach Metodu](../windows/comptr-attach-method.md)|Geçerli şablon türü parametresi tarafından belirtilen arabirim türü bu ComPtr ilişkilendirir.|  
|[ComPtr::CopyTo Metodu](../windows/comptr-copyto-method.md)|Belirtilen çıkış işaretçisi için bu ComPtr ile ilişkili geçerli ya da belirtilen arabirimi kopyalar.|  
|[ComPtr::Detach Metodu](../windows/comptr-detach-method.md)|Bu ComPtr temsil ettiği arabiriminden keser.|  
|[ComPtr::Get Metodu](../windows/comptr-get-method.md)|Bu ComPtr ile ilişkili arayüzü için bir işaretçi alır.|  
|[ComPtr::GetAddressOf Metodu](../windows/comptr-getaddressof-method.md)|Adresini alır [ptr_](../windows/comptr-ptr-data-member.md) bu ComPtr tarafından temsil edilen arayüzü için bir işaretçi içeriyor veri üyesi.|  
|[ComPtr::ReleaseAndGetAddressOf Metodu](../windows/comptr-releaseandgetaddressof-method.md)|Bu ComPtr ile ilişkili arabiriminin serbest bırakır ve adresini alır [ptr_](../windows/comptr-ptr-data-member.md) yayımlanan arayüzü için bir işaretçi içeriyor veri üyesi.|  
|[ComPtr::Reset](../windows/comptr-reset.md)|Bu ComPtr ile ilişkili arabirimi işaretçisi tüm başvurularını serbest bırakır.|  
|[ComPtr::Swap Metodu](../windows/comptr-swap-method.md)|Belirtilen ComPtr tarafından yönetilen arabirimi geçerli ComPtr tarafından yönetilen arabirimi değiş tokuş eder.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtr::InternalAddRef Metodu](../windows/comptr-internaladdref-method.md)|Bu ComPtr ile ilişkili arabiriminin başvurusu sayısını artırır.|  
|[ComPtr::InternalRelease Metodu](../windows/comptr-internalrelease-method.md)|Bu ComPtr ile ilişkili arabiriminin bir COM yayın işlemi gerçekleştirir.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtr::operator Microsoft::WRL::Details::BoolType İşleci](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Bir ComPtr bir arabirim nesne ömrü yönetme olup olmadığını gösterir.|  
|[ComPtr::operator& İşleci](../windows/comptr-operator-ampersand-operator.md)|Geçerli ComPtr adresini alır.|  
|[ComPtr::operator= İşleci](../windows/comptr-operator-assign-operator.md)|Bir değer için geçerli ComPtr atar.|  
|[ComPtr::operator-> İşleci](../windows/comptr-operator-arrow-operator.md)|Geçerli şablon parametresi tarafından belirtilen tür için bir işaretçi alır.|  
|[ComPtr::operator== İşleci](../windows/comptr-operator-equality-operator.md)|İki ComPtr nesnenin eşit olup olmadığını gösterir.|  
|[ComPtr::operator!= İşleci](../windows/comptr-operator-inequality-operator.md)|İki ComPtr nesnenin eşit olup olmadığını gösterir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ComPtr::ptr_ Veri Üyesi](../windows/comptr-ptr-data-member.md)|İle ilişkili ve bu ComPtr tarafından yönetilen arabirimi için bir işaretçi içeriyor.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)