---
title: CAnimationRect sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b08f8d5ad1fa7c925e3a6dc2243079aba21452b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="canimationrect-class"></a>CAnimationRect sınıfı
İki tarafı da animasyonlu dikdörtgen işlevlerini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|Fazla Yüklendi. Bir animasyon rect nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|Sol, üst, sağ ve alt koordinatları için geçişleri ekler.|  
|[CAnimationRect::GetBottom](#getbottom)|Alt koordinat temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Dikdörtgenin sınırları için varsayılan değerleri döndürür.|  
|[CAnimationRect::GetLeft](#getleft)|Sol koordinatını temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationRect::GetRight](#getright)|Erişim için doğru koordinat temsil eden CAnimationVariable sağlar.|  
|[CAnimationRect::GetTop](#gettop)|Üst koordinat temsil eden CAnimationVariable erişim sağlar.|  
|[CAnimationRect::GetValue](#getvalue)|Geçerli bir değer döndürür.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Varsayılan değer ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|Bir CAnimationRect için RECT. dönüştürür|  
|[CAnimationRect::operator =](#operator_eq)|Rect için CAnimationRect atar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Dikdörtgen boyutu sabit sahip olup olmadığını belirtir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Alt temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|Sol temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|Sağ temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|Animasyon dikdörtgen ilk boyutunu belirtir.|  
|[CAnimationRect::m_topValue](#m_topvalue)|Üst temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationRect sınıfı dört CAnimationVariable nesneleri yalıtır ve uygulamalarda dikdörtgen temsil edebilir. Bu sınıf uygulamada kullanmak için yalnızca bu sınıfın bir nesnesi örneği, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve her geçiş için sol, sağ üst ve alt koordinatlara uygulanacak AddTransition çağırın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationRect::AddTransition  
 Sol, üst, sağ ve alt koordinatları için geçişleri ekler.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>Parametreler  
 `pLeftTransition`  
 Sol tarafta için geçişi belirtir.  
  
 `pTopTransition`  
 Üst tarafı için geçiş belirtir.  
  
 `pRightTransition`  
 Geçiş için sağ tarafında belirtir.  
  
 `pBottomTransition`  
 Alt kenar için geçişi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Her bir dikdörtgen kenarı animasyon değişkenleri uygulanacak geçişleri iç listesini belirtilen geçişleri eklemek için bu işlevini çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listede depolanmış. Geçişleri (belirli bir değeri bir film şeridi eklenebilir) uygulanır CAnimationController::AnimateGroup çağırdığınızda. Bir geçiş dikdörtgen yanları biri için geçerli gerekmiyorsa, NULL geçirebilirsiniz.  
  
##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect  
 CAnimationRect nesnesi oluşturur.  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Varsayılan dikdörtgen belirtir.  
  
 `nGroupID`  
 Grup kimliğini belirtir.  
  
 `nObjectID`  
 Nesne kimliğini belirtir.  
  
 `dwUserData`  
 Kullanıcı tanımlı veri belirtir.  
  
 `pt`  
 Sol üst köşede koordinatı.  
  
 `sz`  
 Dikdörtgen boyutu.  
  
 `nLeft`  
 Sol bağlı koordinatını belirtir.  
  
 `nTop`  
 Bağlı üst koordinatını belirtir.  
  
 `nRight`  
 Sağ bağlı koordinatını belirtir.  
  
 `nBottom`  
 Bağlı alt koordinatını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne için varsayılan değerlerle sol, üst, sağ ve alt, nesne kimliği ve 0 olarak ayarlanacak grup kimliği oluşturulur. SetDefaultValue ve SetID kullanarak çalışma zamanında daha sonra değiştirilebilir.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList  
 Kapsüllenmiş animasyon değişkenleri bir listesine koyar.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parametreler  
 `lst`  
 İşlevi döndüğünde dikdörtgen koordinatlarını temsil eden dört CAnimationVariable nesnelerine işaretçiler içerir.  
  
##  <a name="getbottom"></a>  CAnimationRect::GetBottom  
 Alt koordinat temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable alt koordinat temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt koordinat temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue  
 Dikdörtgenin sınırları için varsayılan değerleri döndürür.  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sol, sağ, üst ve alt için varsayılan değerleri içeren bir CRect değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevini çağırın.  
  
##  <a name="getleft"></a>  CAnimationRect::GetLeft  
 Sol koordinatını temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable sol koordinatını temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Sol koordinatını temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getright"></a>  CAnimationRect::GetRight  
 Erişim için doğru koordinat temsil eden CAnimationVariable sağlar.  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable sağ koordinat temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan CAnimationVariable sağ koordinat temsil eden doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="gettop"></a>  CAnimationRect::GetTop  
 Üst koordinat temsil eden CAnimationVariable erişim sağlar.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş CAnimationVariable üst koordinat temsil eden bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Üst koordinat temsil eden temel CAnimationVariable doğrudan erişmek için bu yöntemi çağırabilirsiniz.  
  
##  <a name="getvalue"></a>  CAnimationRect::GetValue  
 Geçerli bir değer döndürür.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Çıktı. Bu yöntem döndürüldüğünde geçerli değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli değer başarıyla alındığında TRUE, Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon dikdörtgen geçerli değerini almak için bu işlevini çağırın. Bu yöntem başarısız olursa veya temel alınan COM için sola nesneleri, üst, sağ ve alt başlatılmamış, rect Oluşturucusu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değeri içerir.  
  
##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize  
 Dikdörtgen boyutu sabit sahip olup olmadığını belirtir.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye true ise, dikdörtgen sabit ve doğru boyutta ve altındaki değerler her zaman sol üst köşede göre sabit boyutlu taşınır hesaplanır. Bu değeri kolayca ekran etrafında dikdörtgen taşımak için TRUE olarak ayarlayın. Bu durumda sağ ve alt koordinatlara uygulanmış geçişler göz ardı edilir. Nesnesi oluşturun ve/veya SetDefaultValue çağrısı boyutu dahili olarak depolanır. Bu üye, varsayılan olarak FALSE değerine ayarlanır.  
  
##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue  
 Alt temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue  
 Sol temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue  
 Sağ temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial  
 Animasyon dikdörtgen ilk boyutunu belirtir.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue  
 Üst temsil eden kapsüllenmiş animasyon değişken animasyon dikdörtgen bağlı.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>  CAnimationRect::operator RECT  
 Bir CAnimationRect için RECT. dönüştürür  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon dikdörtgen RECT. gibi geçerli değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev GetValue dahili olarak çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen RECT tüm dikdörtgen koordinatları için varsayılan değerleri içerir.  
  
##  <a name="operator_eq"></a>  CAnimationRect::operator =  
 Rect için CAnimationRect atar.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Animasyon dikdörtgen yeni değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç oluşturulmuş durumunda, renk bileşenleri için temel alınan COM nesneleri yeniden SetDefaultValue çağırdığı için animasyon başlamadan önce bunu yapmak için önerilen. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue  
 Varsayılan değer ayarlar.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 `rect`  
 Sol, üst, sağ ve alt yeni varsayılan değerleri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon nesnesine bir varsayılan değeri ayarlamak için bu işlevi kullanın. Bu yöntemleri dikdörtgenin sınırları için varsayılan değerleri atar. Ayrıca oluşturduysanız, temel alınan COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
