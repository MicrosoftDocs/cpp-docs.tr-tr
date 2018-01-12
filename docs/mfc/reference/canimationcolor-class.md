---
title: "CAnimationColor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs: C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd6ec3b6d8ee6a37fbe189ff70a2a633cfda9c8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimationcolor-class"></a>CAnimationColor sınıfı
Kırmızı, yeşil ve mavi bileşenlerini animasyonlu renkli işlevlerini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|Fazla Yüklendi. Bir animasyon renk nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|Kırmızı, yeşil ve mavi bileşenleri için geçişleri ekler.|  
|[CAnimationColor::GetB](#getb)|Mavi bileşenini temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Renk bileşenleri için varsayılan değerleri döndürür.|  
|[CAnimationColor::GetG](#getg)|Yeşil bileşenini temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationColor::GetR](#getr)|Kırmızı bileşenini temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationColor::GetValue](#getvalue)|Geçerli bir değer döndürür.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Varsayılan değer ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|Renk için CAnimationColor atar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|Animasyon rengin mavi bileşenini temsil eden kapsüllenmiş animasyon değişken.|  
|[CAnimationColor::m_gValue](#m_gvalue)|Animasyon rengin yeşil bileşenini temsil eden kapsüllenmiş animasyon değişken.|  
|[CAnimationColor::m_rValue](#m_rvalue)|Animasyon rengi kırmızı bileşenini temsil eden kapsüllenmiş animasyon değişken.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationColor sınıf üç CAnimationVariable nesne yalıtır ve uygulamalarda renk temsil edebilir. Örneğin, renkleri ekranında herhangi bir nesnenin animasyon uygulamak için bu sınıf kullanabilirsiniz (metin rengi gibi arka plan rengi vb.). Bu sınıf uygulamada kullanmak için yalnızca bu sınıfın bir nesnesi örneği, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve kırmızı, yeşil ve mavi bileşenlerine uygulanabilir AddTransition her geçiş için çağırın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationColor::AddTransition  
 Kırmızı, yeşil ve mavi bileşenleri için geçişleri ekler.  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>Parametreler  
 `pRTransition`  
 Kırmızı bileşeni için geçişi.  
  
 `pGTransition`  
 Yeşil bileşeni için geçişi.  
  
 `pBTransition`  
 Mavi bileşeni için geçişi.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen geçişleri renk bileşenleri temsil eden animasyon değişkenlere uygulanacak geçişleri iç listesine eklemek için bu işlevini çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listede depolanmış. Geçişleri (belirli bir değeri bir film şeridi eklenebilir) uygulanır CAnimationController::AnimateGroup çağırdığınızda. Renk bileşenlerden biri için bir geçiş uygulanacak gerekmiyorsa, NULL geçirebilirsiniz.  
  
##  <a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 CAnimationColor nesnesi oluşturur.  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Varsayılan rengini belirtir.  
  
 `nGroupID`  
 Grup kimliğini belirtir.  
  
 `nObjectID`  
 Nesne kimliğini belirtir.  
  
 `dwUserData`  
 Kullanıcı tanımlı veri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne için varsayılan değerlerle kırmızı, yeşil, mavi, nesne kimliği ve 0 olarak ayarlanacak grup kimliği oluşturulur. SetDefaultValue ve SetID kullanarak çalışma zamanında daha sonra değiştirilebilir.  
  
##  <a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 Kapsüllenmiş animasyon değişkenleri bir listesine koyar.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parametreler  
 `lst`  
 İşlevi döndüğünde, kırmızı, yeşil ve mavi bileşenlerini temsil eden üç CAnimationVariable nesnelerine işaretçiler içerir.  
  
##  <a name="getb"></a>CAnimationColor::GetB  
 Mavi bileşenini temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable mavi bileşenini temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Mavi bileşenini temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 Renk bileşenleri için varsayılan değerleri döndürür.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 RGB bileşenleri için varsayılan değerleri içeren bir COLORREF değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevini çağırın.  
  
##  <a name="getg"></a>CAnimationColor::GetG  
 Yeşil bileşenini temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable temsil eden yeşil bileşenine bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan CAnimationVariable temsil eden yeşil bileşen doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getr"></a>CAnimationColor::GetR  
 Kırmızı bileşenini temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable kırmızı bileşenini temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Kırmızı bileşenini temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getvalue"></a>CAnimationColor::GetValue  
 Geçerli bir değer döndürür.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Çıktı. Bu yöntem döndürüldüğünde geçerli değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli değer başarıyla alındığında TRUE, Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon renk geçerli değerini almak için bu işlevini çağırın. Bu yöntem başarısız ya da henüz başlatılmamış renk bileşenleri için temel alınan COM nesneleri, renk Oluşturucusu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değeri içerir.  
  
##  <a name="m_bvalue"></a>CAnimationColor::m_bValue  
 Animasyon rengin mavi bileşenini temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>CAnimationColor::m_gValue  
 Animasyon rengin yeşil bileşenini temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>CAnimationColor::m_rValue  
 Animasyon rengi kırmızı bileşenini temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_eq"></a>CAnimationColor::operator =  
 Renk için CAnimationColor atar.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Yeni değer animasyon rengini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç oluşturulmuş durumunda, renk bileşenleri için temel alınan COM nesneleri yeniden SetDefaultValue çağırdığı için animasyon başlamadan önce bunu yapmak için önerilen. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
##  <a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 Varsayılan değer ayarlar.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 `color`  
 Kırmızı, yeşil ve mavi bileşenleri için yeni varsayılan değerleri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon nesnesine bir varsayılan değeri ayarlamak için bu işlevi kullanın. Bu yöntem, animasyon rengi renk bileşenleri için varsayılan değerleri atar. Ayrıca oluşturduysanız, temel alınan COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
