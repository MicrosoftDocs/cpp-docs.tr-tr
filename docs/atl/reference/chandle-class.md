---
title: "CHandle sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
dev_langs: C++
helpviewer_keywords: CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ed254b49c61f873e1d85fd0600c371c03ac246a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chandle-class"></a>CHandle sınıfı
Bu sınıf oluşturmak ve bir tanıtıcı nesnesi kullanmak için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CHandle
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Oluşturucu.|  
|[CHandle:: ~ CHandle](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Eklemek için bu yöntemi çağırın `CHandle` varolan işlenecek nesne.|  
|[CHandle::Close](#close)|Kapatmak için bu yöntemi çağırın bir `CHandle` nesnesi.|  
|[CHandle::Detach](#detach)|Gelen bir tanıtıcı ayırmak için bu yöntemi çağırın bir `CHandle` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHandle::operator TANITICISI](#operator_handle)|Saklı tanıtıcı değerini döndürür.|  
|[CHandle::operator =](#operator_eq)|Atama işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|Tanıtıcıyı depolar üye değişkeni.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CHandle` nesnesi tanıtıcı gerekli olduğunda kullanılabilir: Ana fark `CHandle` nesne otomatik olarak silinecek.  
  
> [!NOTE]
>  Başkalarının INVALID_HANDLE_VALUE kullanırken bazı API işlevleri NULL bir boş veya geçersiz tanıtıcı kullanın. `CHandle`yalnızca kullanır bilir ve NULL INVALID_HANDLE_VALUE gerçek bir tanıtıcı kabul eder. INVALID_HANDLE_VALUE döndürmesi bir API çağırırsanız, bu değerin çağırmadan önce denetlemelisiniz [CHandle::Attach](#attach) veya ona geçirme `CHandle` oluşturucusu ve bunun yerine NULL geçirin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="attach"></a>CHandle::Attach  
 Eklemek için bu yöntemi çağırın `CHandle` varolan işlenecek nesne.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `h`  
 `CHandle`tanıtıcı sahipliğini `h`.  
  
### <a name="remarks"></a>Açıklamalar  
 Atar `CHandle` nesnesine `h` işler. Hatalarını düzeltir derlemelerde bir ATLASSERT gerçekleştirilecektir `h` null. Herhangi bir onay tanıtıcı geçerliliğini için yapılır.  
  
##  <a name="chandle"></a>CHandle::CHandle  
 Oluşturucu.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `h`  
 Varolan bir tanıtıcısı veya `CHandle`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir `CHandle` nesnesi, isteğe bağlı olarak var olan bir tanıtıcı kullanılarak veya `CHandle` nesnesi.  
  
##  <a name="dtor"></a>CHandle:: ~ CHandle  
 Yok Edicisi.  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Serbest bırakma `CHandle` çağırarak nesne [CHandle::Close](#close).  
  
##  <a name="close"></a>CHandle::Close  
 Kapatmak için bu yöntemi çağırın bir `CHandle` nesnesi.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir açık nesne tanıtıcısı kapatır. Tanıtıcı servis talebi if olmayacaktır NULL ise **Kapat** zaten adlı bir ATLASSERT hata ayıklama derlemelerinde gerçekleştirilecektir.  
  
##  <a name="detach"></a>CHandle::Detach  
 Gelen bir tanıtıcı ayırmak için bu yöntemi çağırın bir `CHandle` nesnesi.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmakta işleyicisini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tanıtıcı sahipliğini serbest bırakır.  
  
##  <a name="m_h"></a>CHandle::m_h  
 Tanıtıcıyı depolar üye değişkeni.  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>CHandle::operator =  
 Atama işleci.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `h`  
 `CHandle`tanıtıcı sahipliğini `h`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir başvuru döndürür `CHandle` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `CHandle` nesne şu anda bir tanıtıcı içerir, kapatılacak. `CHandle` Geçirilen NULL olarak ayarlamak, tanıtıcı başvuru olacaktır nesne. Bu, iki sağlar `CHandle` nesneleri hiçbir zaman aynı etkin tanıtıcıyı içerir.  
  
##  <a name="operator_handle"></a>CHandle::operator TANITICISI  
 Saklı tanıtıcı değerini döndürür.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Depolanan değeri döndürür [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
