---
title: "CAnimationPoint sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
dev_langs: C++
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ab685c223c4a86c35ba0feb578d93f58844734b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimationpoint-class"></a>CAnimationPoint sınıfı
Koordinatları animasyonlu nokta işlevlerini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Fazla Yüklendi. CAnimationPoint nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|X için geçişleri ekler ve Y koordinatları.|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|X için varsayılan değerleri döndürür ve Y koordinatları.|  
|[CAnimationPoint::GetValue](#getvalue)|Geçerli bir değer döndürür.|  
|[CAnimationPoint::GetX](#getx)|Erişim için CAnimationVariable X koordinatı sağlar.|  
|[CAnimationPoint::GetY](#gety)|Erişim için CAnimationVariable Y koordinatı sağlar.|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Varsayılan değer ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Bir CAnimationPoint bir CPoint dönüştürür.|  
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint ptSrc atar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|X temsil eden kapsüllenmiş animasyon değişken animasyon noktasının koordinat.|  
|[CAnimationPoint::m_yValue](#m_yvalue)|Animasyon noktasının Y koordinatı temsil eden kapsüllenmiş animasyon değişken.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationPoint sınıf iki CAnimationVariable nesneleri yalıtır ve uygulamalarda bir nokta temsil edebilir. Örneğin, bu sınıfın (örneğin, metin dizesi, daire, noktası vb.) ekrandaki herhangi bir nesnenin konumunu hareketli hale getirmeyi için kullanabilirsiniz. Bu sınıf uygulamada kullanmak için yalnızca bu sınıfın bir nesnesi örneği, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve uygulanacak AddTransition her geçiş için çağırın X ve/veya Y koordinatları.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationPoint::AddTransition  
 X için geçişleri ekler ve Y koordinatları.  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>Parametreler  
 `pXTransition`  
 Geçiş için koordinatları X için bir işaretçi.  
  
 `pYTransition`  
 Bir işaretçi geçiş y koordinatı.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen geçişler için X animasyon değişkenlere uygulanacak geçişlerinin iç listesine eklemek için bu işlevi çağırmak ve Y koordinatları. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listede depolanmış. Geçişleri (belirli bir değeri bir film şeridi eklenebilir) uygulanır CAnimationController::AnimateGroup çağırdığınızda. Bir geçiş koordinatları biri için geçerli gerekmiyorsa, NULL geçirebilirsiniz.  
  
##  <a name="canimationpoint"></a>CAnimationPoint::CAnimationPoint  
 CAnimationPoint nesnesi oluşturur.  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptDefault`  
 Varsayılan noktası koordinatları belirtir.  
  
 `nGroupID`  
 Grup kimliğini belirtir.  
  
 `nObjectID`  
 Nesne kimliğini belirtir.  
  
 `dwUserData`  
 Kullanıcı tanımlı veri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan özelliklerine sahip CAnimationPoint nesnesi oluşturur: varsayılan noktası koordinatları, grup kimliği ve nesne kimliği 0 olarak ayarlanmış.  
  
##  <a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList  
 Kapsüllenmiş animasyon değişkenleri bir listesine koyar.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parametreler  
 `lst`  
 İşlevi döndüğünde, X ve Y koordinatları temsil eden iki CAnimationVariable nesnelerine işaretçiler içerir.  
  
##  <a name="getdefaultvalue"></a>CAnimationPoint::GetDefaultValue  
 X için varsayılan değerleri döndürür ve Y koordinatları.  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir nokta içeren varsayılan değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevini çağırın.  
  
##  <a name="getvalue"></a>CAnimationPoint::GetValue  
 Geçerli bir değer döndürür.  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptValue`  
 Çıktı. Bu yöntem döndürüldüğünde geçerli değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli değer başarıyla alındığında TRUE, Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon noktasının geçerli değerini almak için bu işlevini çağırın. Bu yöntem başarısız olursa veya temel alınan COM nesneleri için X ve Y koordinatları başlatılmamış, ptValue Oluşturucusu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değeri içerir.  
  
##  <a name="getx"></a>CAnimationPoint::GetX  
 Erişim için CAnimationVariable X koordinatı sağlar.  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable X temsil eden bir başvuru koordinatı.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan CAnimationVariable X temsil eden doğrudan erişmek için bu yöntemi çağırın koordinatı.  
  
##  <a name="gety"></a>CAnimationPoint::GetY  
 Erişim için CAnimationVariable Y koordinatı sağlar.  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable Y koordinatını temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Y koordinatını temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="m_xvalue"></a>CAnimationPoint::m_xValue  
 X temsil eden kapsüllenmiş animasyon değişken animasyon noktasının koordinat.  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>CAnimationPoint::m_yValue  
 Animasyon noktasının Y koordinatı temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>CAnimationPoint::operator CPoint  
 Bir CAnimationPoint bir CPoint dönüştürür.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 CAnimationPoint CPoint olarak geçerli değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev GetValue dahili olarak çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen noktası X için varsayılan değerleri içerir ve Y koordinatları.  
  
##  <a name="operator_eq"></a>CAnimationPoint::operator =  
 CAnimationPoint ptSrc atar.  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptSrc`  
 CPoint veya NOKTASINA başvuruyor.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationPoint ptSrc atar. Bu işleç SetDefaultValue, çağırdığı için oluşturulmuş durumunda X ve Y koordinatları için animasyon başlamadan önce temel alınan COM yeniden oluşturur nesneleri olduğunu yapmak için önerilen. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
##  <a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue  
 Varsayılan değer ayarlar.  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptDefault`  
 Varsayılan nokta değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon nesnesine bir varsayılan değeri ayarlamak için bu işlevi kullanın. Bu yöntemleri atar varsayılan değerler animasyon noktasının X ve Y koordinatları. Ayrıca oluşturduysanız, temel alınan COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
