---
title: "CBaseTransition sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
dev_langs: C++
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ba6d85437845e924dcc3c7d36005b20fef280b13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cbasetransition-class"></a>CBaseTransition sınıfı
Temel bir geçişi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-enumerations"></a>Ortak numaralandırmaları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseTransition::TRANSITION_TYPE numaralandırması](#transition_type_enumeration)|Şu anda Windows animasyon API MFC uygulaması tarafından desteklenen geçiş türleri tanımlar.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|Temel transtion nesnesi oluşturur.|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Yok Edicisi. Bir geçiş nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Bir geçiş için film şeridi ekler.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Bir geçiş için film şeridi ekler.|  
|[CBaseTransition::Clear](#clear)|Sürümler IUIAnimationTransition COM nesnesi kapsüllenir.|  
|[CBaseTransition::Create](#create)|Bir COM geçiş oluşturur.|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Döndürür ana kare başlatın.|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Bir işaretçi ilgili değişkeni döndürür.|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Döndürür ana kare başlatın.|  
|[CBaseTransition::GetTransition](#gettransition)|Fazla Yüklendi. Bir işaretçi temel alınan COM geçiş nesnesi döndürür.|  
|[CBaseTransition::GetType](#gettype)|Geçiş türü döndürür.|  
|[CBaseTransition::IsAdded](#isadded)|Bir geçiş için film şeridi eklenmiş olup olmadığını bildirir.|  
|[CBaseTransition::SetKeyframes](#setkeyframes)|Bir geçiş için ana kare ayarlar.|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Animasyon değişkeni ve geçiş arasında bir ilişki kurar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|Bir geçiş için film şeridi eklenmiş olup olmadığını belirtir.|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Geçiş işleminin sonunda belirtir kareyi gösteren bir işaretçi depolar.|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|M_transition içinde depolanan geçiş ile Animasyonlu bir animasyon değişkeni için bir işaretçi.|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Geçişin başlangıcını belirtir kareyi gösteren bir işaretçi depolar.|  
|[CBaseTransition::m_transition](#m_transition)|Bir işaretçi IUIAnimationTransition depolar. Bir COM geçiş nesnesi oluşturulmadı yoksa NULL.|  
|[CBaseTransition::m_type](#m_type)|Geçiş türü depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf IUIAnimationTransition arabirimi yalıtır ve tüm geçişler için bir taban sınıf görevi görür.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="_dtorcbasetransition"></a>CBaseTransition:: ~ CBaseTransition  
 Yok Edicisi. Bir geçiş nesnesi yok çağrılır.  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard  
 Bir geçiş için film şeridi ekler.  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStoryboard`  
 İlgili değişken animasyon film şeridi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, geçiş için film şeridi başarıyla eklendi.  
  
### <a name="remarks"></a>Açıklamalar  
 Film şeridi ilgili değişken geçiş uygulanır. Bu değişken bu film şeridi uygulanan ilk geçiş varsa geçişi film şeridi başlangıcında başlar. Aksi takdirde, geçiş değişkenine eklenen en son geçiş eklenir.  
  
##  <a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes  
 Bir geçiş için film şeridi ekler.  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStoryboard`  
 İlgili değişken animasyon film şeridi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE, geçiş için film şeridi başarıyla eklendi.  
  
### <a name="remarks"></a>Açıklamalar  
 Film şeridi ilgili değişken geçiş uygulanır. Başlangıç ana kareyi belirtildiyse, geçiş sırasında bu anahtar kare başlar. Son ana kareyi belirtilmişse başlangıç ana kareyi geçiş başlar ve ve son kareyi durdurur. Geçiş belirtilen bir süre parametresi ile oluşturulmuşsa, sürenin başlangıç ve bitiş ana kareler arasındaki süreyi üzerine yazılır. Hiçbir anahtar kare belirtilmişse geçişi değişkenine eklenen en son geçiş eklenir.  
  
##  <a name="cbasetransition"></a>CBaseTransition::CBaseTransition  
 Temel transtion nesnesi oluşturur.  
  
```  
CBaseTransition();
```  
  
##  <a name="clear"></a>CBaseTransition::Clear  
 Sürümler IUIAnimationTransition COM nesnesi kapsüllenir.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, IUITransition arabirimi sızıntısını önlemek için türetilmiş sınıf oluşturma yöntemi çağrılmalıdır.  
  
##  <a name="create"></a>CBaseTransition::Create  
 Bir COM geçiş oluşturur.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pLibrary`  
 Standart geçişleri oluşturur geçiş kitaplığı için bir işaretçi. Bu özel geçişler için NULL olabilir.  
  
 `pFactory`  
 Özel geçişler oluşturur geçiş üreteci için bir işaretçi. Bu, standart geçişler için NULL olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir geçiş COM Nesne başarıyla oluşturuldu, TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta geçersiz kılınmalıdır saf bir sanal işlev budur. COM geçiş nesnesini örneği oluşturmak için çerçevesi tarafından çağrılır.  
  
##  <a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe  
 Döndürür ana kare başlatın.  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi bir ana kare ya da bir geçiş anahtar kare arasında eklenmez yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından SetKeyframes önceden ayarlanmış bir ana kare nesneye erişmek için kullanılabilir. Geçişler film şeridi eklenirken üst düzey kod tarafından çağrılır.  
  
##  <a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable  
 Bir işaretçi ilgili değişkeni döndürür.  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi animasyon değişkeni ya da bir animasyon değişkeni tarafından SetRelatedVariable ayarlı değil yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili animasyon değişkeni için bir erişimci budur.  
  
##  <a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe  
 Döndürür ana kare başlatın.  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi bir ana kare ya da bir geçiş bir ana kare başlamamalıdır yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından SetKeyframes önceden ayarlanmış bir ana kare nesneye erişmek için kullanılabilir. Geçişler film şeridi eklenirken üst düzey kod tarafından çağrılır.  
  
##  <a name="gettransition"></a>CBaseTransition::GetTransition  
 Bir işaretçi temel alınan COM geçiş nesnesi döndürür.  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>Parametreler  
 `pLibrary`  
 Standart geçişleri oluşturur geçiş kitaplığı için bir işaretçi. Bu özel geçişler için NULL olabilir.  
  
 `pFactory`  
 Özel geçişler oluşturur geçiş üreteci için bir işaretçi. Bu, standart geçişler için NULL olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi IUIAnimationTransition veya geçiş temel oluşturulamıyorsa boş.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, temel alınan COM geçiş nesnesine bir işaretçi döndürür ve gerekirse oluşturur.  
  
##  <a name="gettype"></a>CBaseTransition::GetType  
 Geçiş türü döndürür.  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRANSITION_TYPE birini değerleri numaralandırılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, türü tarafından geçiş nesneyi tanımlamak için kullanılabilir. Tür oluşturucu türetilmiş bir sınıf içinde ayarlanır.  
  
##  <a name="isadded"></a>CBaseTransition::IsAdded  
 Bir geçiş için film şeridi eklenmiş olup olmadığını bildirir.  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir geçiş bir film şeridi Aksi takdirde FALSE eklenip eklenmediğini TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak, üst düzey kod film şeridi geçişleri eklediğinde dahili olarak ayarlanır.  
  
##  <a name="m_badded"></a>CBaseTransition::m_bAdded  
 Bir geçiş için film şeridi eklenmiş olup olmadığını belirtir.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe  
 Geçiş işleminin sonunda belirtir kareyi gösteren bir işaretçi depolar.  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable  
 M_transition içinde depolanan geçiş ile Animasyonlu bir animasyon değişkeni için bir işaretçi.  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe  
 Geçişin başlangıcını belirtir kareyi gösteren bir işaretçi depolar.  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="m_transition"></a>CBaseTransition::m_transition  
 Bir işaretçi IUIAnimationTransition depolar. Bir COM geçiş nesnesi oluşturulmadı yoksa NULL.  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="m_type"></a>CBaseTransition::m_type  
 Geçiş türü depolar.  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="setkeyframes"></a>CBaseTransition::SetKeyframes  
 Bir geçiş için ana kare ayarlar.  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStart`  
 Geçişin başlangıcını belirtir ana kare.  
  
 `pEnd`  
 Geçiş işleminin sonunda belirtir ana kare.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sonra belirtilen ana kare başlatmak ve isteğe bağlı olarak, bekleme NULL değilse sonlandırmak için geçiş söyler belirtilen kareyi önce. Geçiş belirtilen bir süre parametresi ile oluşturulmuşsa, sürenin başlangıç ve bitiş ana kareler arasındaki süreyi üzerine yazılır.  
  
##  <a name="setrelatedvariable"></a>CBaseTransition::SetRelatedVariable  
 Animasyon değişkeni ve geçiş arasında bir ilişki kurar.  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pVariable`  
 İlgili animasyon değişkeni için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon değişkeni ve geçiş arasında bir ilişki kurar. Yalnızca bir değişken için bir geçiş uygulanabilir.  
  
##  <a name="transition_type_enumeration"></a>CBaseTransition::TRANSITION_TYPE numaralandırması  
 Şu anda Windows animasyon API MFC uygulaması tarafından desteklenen geçiş türleri tanımlar.  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir geçiş türü belirli geçiş oluşturucuda ayarlanır. Örneğin, CSinusoidalTransitionFromRange için SINUSOIDAL_FROM_RANGE türünü ayarlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
