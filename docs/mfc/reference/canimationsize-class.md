---
title: "CAnimationSize sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs: C++
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2acbdad3ec5b08ef5d83b3a6cfdb2eadd3c0e17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimationsize-class"></a>CAnimationSize sınıfı
Olan boyutlar animasyonlu boyutu nesnesinin işlevselliğini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|Fazla Yüklendi. Bir animasyon boyutu nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|Genişlik ve yükseklik geçişleri ekler.|  
|[CAnimationSize::GetCX](#getcx)|Genişlik temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationSize::GetCY](#getcy)|Yükseklik temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Genişlik ve yükseklik için varsayılan değerleri döndürür.|  
|[CAnimationSize::GetValue](#getvalue)|Geçerli bir değer döndürür.|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Varsayılan değer ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|Bir CAnimationSize bir CSize dönüştürür.|  
|[CAnimationSize::operator =](#operator_eq)|CAnimationSize szSrc atar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|Animasyon boyutu genişliğini temsil eden kapsüllenmiş animasyon değişken.|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|Animasyon boyutunun yüksekliğini temsil eden kapsüllenmiş animasyon değişken.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationSize sınıf iki CAnimationVariable nesneleri yalıtır ve uygulamalarda bir boyutu temsil edebilir. Örneğin, herhangi iki boyutunu animasyon uygulamak için bu sınıf kullanabilirsiniz ekranında boyutlu nesne (dikdörtgen gibi kontrol vb.). Bu sınıf uygulamada kullanmak için yalnızca bu sınıfın bir nesnesi örneği, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve genişlik ve/veya yükseklik uygulanacak AddTransition her geçiş için çağırın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationSize::AddTransition  
 Genişlik ve yükseklik geçişleri ekler.  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCXTransition`  
 Width için geçiş için bir işaretçi.  
  
 `pCYTransition`  
 Yükseklik için geçiş için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen geçişleri iç genişliği ve yüksekliği için animasyon değişkenlere uygulanacak geçişleri listesine eklemek için bu işlevini çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listede depolanmış. Geçişleri (belirli bir değeri bir film şeridi eklenebilir) uygulanır CAnimationController::AnimateGroup çağırdığınızda. Bir geçiş boyutları biri için geçerli gerekmiyorsa, NULL geçirebilirsiniz.  
  
##  <a name="canimationsize"></a>CAnimationSize::CAnimationSize  
 Bir animasyon boyutu nesnesi oluşturur.  
  
```  
CAnimationSize();

 
CAnimationSize(
    const CSize& szDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `szDefault`  
 Varsayılan boyutunu belirtir.  
  
 `nGroupID`  
 Grup kimliğini belirtir.  
  
 `nObjectID`  
 Nesne kimliğini belirtir.  
  
 `dwUserData`  
 Kullanıcı tanımlı veri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne kimliği ve 0 olarak ayarlanacak Grup Kimliği nesneyi genişlik, yükseklik için varsayılan değerlerle oluşturulur. SetDefaultValue ve SetID kullanarak çalışma zamanında daha sonra değiştirilebilir.  
  
##  <a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList  
 Kapsüllenmiş animasyon değişkenleri bir listesine koyar.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parametreler  
 `lst`  
 İşlevi döndüğünde, genişlik ve yükseklik temsil eden iki CAnimationVariable nesnelerine işaretçiler içerir.  
  
##  <a name="getcx"></a>CAnimationSize::GetCX  
 Genişlik temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable genişliği temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan CAnimationVariable genişliği temsil eden doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getcy"></a>CAnimationSize::GetCY  
 Yükseklik temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable yüksekliğini temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Yükseklik temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue  
 Genişlik ve yükseklik için varsayılan değerleri döndürür.  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan değerleri içeren bir CSize nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevini çağırın.  
  
##  <a name="getvalue"></a>CAnimationSize::GetValue  
 Geçerli bir değer döndürür.  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `szValue`  
 Çıktı. Bu yöntem döndürüldüğünde geçerli değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli değer başarıyla alındığında TRUE, Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon boyutu geçerli değerini almak için bu işlevini çağırın. Bu yöntem başarısız ya da henüz başlatılmamış genişlik ve boyutu için temel alınan COM nesneleri, szValue Oluşturucusu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değeri içerir.  
  
##  <a name="m_cxvalue"></a>CAnimationSize::m_cxValue  
 Animasyon boyutu genişliğini temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_cxValue;  
```  
  
##  <a name="m_cyvalue"></a>CAnimationSize::m_cyValue  
 Animasyon boyutunun yüksekliğini temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_cyValue;  
```  
  
##  <a name="operator_csize"></a>CAnimationSize::operator CSize  
 Bir CAnimationSize bir CSize dönüştürür.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon boyutu CSize olarak geçerli değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev GetValue dahili olarak çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen boyutu genişlik ve yükseklik için varsayılan değerleri içerecektir.  
  
##  <a name="operator_eq"></a>CAnimationSize::operator =  
 CAnimationSize szSrc atar.  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `szSrc`  
 CSize veya boyutunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationSize szSrc atar. Bu işleç oluşturulmuş durumunda, genişlik ve yükseklik için temel alınan COM nesneleri yeniden SetDefaultValue çağırdığı için animasyon başlamadan önce bunu yapmak için önerilen. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
##  <a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue  
 Varsayılan değer ayarlar.  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `szDefault`  
 Yeni varsayılan boyutunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon nesnesine bir varsayılan değeri ayarlamak için bu işlevi kullanın. Bu yöntem, genişlik ve yükseklik animasyon boyutu için varsayılan değerleri atar. Ayrıca oluşturduysanız, temel alınan COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
