---
title: "CAnimationVariable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
dev_langs: C++
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bc59fa4597bff59901ef77b0a661cf406bda6b29
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="canimationvariable-class"></a>CAnimationVariable sınıfı
Bir animasyon değişkeni temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Bir animasyon değişken nesnesi oluşturur.|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Yok Edicisi. Bir CAnimationVariable nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|Bir geçiş ekler.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Geçişler film şeridi için iç listeden ekler.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Geçişleri temizler.|  
|[CAnimationVariable::Create](#create)|Animasyon değişken COM nesnesini oluşturur.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|Bu animasyon değişkenine uygulanacak tüm geçişleri oluşturur.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Etkinleştirir veya IntegerValueChanged olay devre dışı bırakır.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Etkinleştirir veya ValueChanged olay devre dışı bırakır.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Varsayılan değerini döndürür.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Üst öğesini döndürür animasyon nesnesi.|  
|[CAnimationVariable::GetValue](#getvalue)|Fazla Yüklendi. Animasyon değişkenin geçerli değeri döndürür.|  
|[CAnimationVariable::GetVariable](#getvariable)|Bir işaretçi IUIAnimationVariable COM nesnesi döndürür.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Varsayılan değer ayarlar ve IUIAnimationVariable COM nesnesi serbest bırakır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Bir animasyon değişkeni ve bir animasyon nesne arasındaki ilişkiyi ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçiş nesneleri silinmesi gerekip gerekmediğini belirtir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|İçin IUIAnimationVariable yayılır varsayılan değeri belirtir.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Bu animasyon değişken animasyon geçişleri listesini içerir.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Bu animasyon değişken yalıtan bir animasyon nesne için bir işaretçi.|  
|[CAnimationVariable::m_variable](#m_variable)|IUIAnimationVariable COM nesnesi için bir işaretçi depolar. COM Nesne henüz oluşturulmamış veya oluşturma başarısız olursa NULL.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationVariable sınıfı IUIAnimationVariable COM nesnesi yalıtır. Ayrıca, bir film şeridi animasyon değişkeninde uygulanacak geçişleri listesini tutar. Bir uygulama animasyonlu değeri, noktası, boyutunu, rengini ve dikdörtgen gösterebilir animasyon nesnelere katıştırılmış CAnimationVariable nesneleri.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CAnimationVariable`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable  
 Yok Edicisi. Bir CAnimationVariable nesnesi yok çağrılır.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>CAnimationVariable::AddTransition  
 Bir geçiş ekler.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTransition`  
 Eklemek için bir geçiş için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir geçiş animasyon değişkenine uygulanacak geçişleri iç listesine eklemek için çağrılır. Bu liste, animasyonun zamanlandığı temizlenmelidir.  
  
##  <a name="applytransitions"></a>CAnimationVariable::ApplyTransitions  
 Geçişler film şeridi için iç listeden ekler.  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parametreler  
 `pController`  
 Üst animasyon denetleyici için bir işaretçi.  
  
 `pStoryboard`  
 Film şeridi bir işaretçi.  
  
 `bDependOnKeyframes`  
 TRUE, bu yöntem ana kare üzerinde bağımlı geçişleri eklemeniz gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem iç listeden film şeridi geçişleri ekler. Ana kare bağlıdır ve ana kare üzerinde bağımlı geçiş ekleme geçişleri eklemek için buna en üst düzey koddan birkaç kez denir. Temel alınan animasyon değişkeni COM nesnesi oluşturulmadı, bu yöntem bu aşamada oluşturur.  
  
##  <a name="canimationvariable"></a>CAnimationVariable::CAnimationVariable  
 Bir animasyon değişken nesnesi oluşturur.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblDefaultValue`  
 Varsayılan değer belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir animasyon değişken nesnesi oluşturur ve varsayılan değerini ayarlar. Bir değişken değil animasyonlu veya animasyon varsayılan değer kullanılır.  
  
##  <a name="cleartransitions"></a>CAnimationVariable::ClearTransitions  
 Geçişleri temizler.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAutodestroy`  
 Bu yöntem geçiş nesneleri silmesi gerekip gerekmediğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm geçişleri geçişleri iç listesinden kaldırır. BAutodestroy TRUE ya da m_bAutodestroyTransitions TRUE geçişleri silinir. Aksi takdirde çağıran geçiş nesneleri serbest bırakma.  
  
##  <a name="create"></a>CAnimationVariable::Create  
 Animasyon değişken COM nesnesini oluşturur.  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>Parametreler  
 `pManager`  
 Animasyon Yöneticisi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon değişken başarıyla oluşturuldu, TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, temel alınan animasyon değişken COM nesnesi oluşturur ve varsayılan değerini ayarlar.  
  
##  <a name="createtransitions"></a>CAnimationVariable::CreateTransitions  
 Bu animasyon değişkenine uygulanacak tüm geçişleri oluşturur.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parametreler  
`pLibrary`  
 Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](https://msdn.microsoft.com/library/windows/desktop/dd371897), standart geçişleri kitaplığı tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçişleri başarıyla oluşturuldu, TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Değişkenin iç geçişler listesine eklenen geçişleri oluşturmak gerektiğinde bu yöntem çerçevesi tarafından çağrılır.  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationVariable::EnableIntegerValueChangedEvent  
 Etkinleştirir veya IntegerValueChanged olay devre dışı bırakır.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pController`  
 Üst denetleyici için bir işaretçi.  
  
 `bEnable`  
 Olay, FALSE - devre dışı bırak olay TRUE - etkinleştirin.  
  
### <a name="remarks"></a>Açıklamalar  
 ValueChanged olay etkinleştirildiğinde, sanal bir yöntem CAnimationController::OnAnimationIntegerValueChanged framework çağırır. Bu olayın işlenmesi için CAnimationController türetilen bir sınıfta geçersiz kılmanız gerekir. Animasyon değişkenin tamsayı değeri her değiştiğinde bu yöntem çağrılır.  
  
##  <a name="enablevaluechangedevent"></a>CAnimationVariable::EnableValueChangedEvent  
 Etkinleştirir veya ValueChanged olay devre dışı bırakır.  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pController`  
 Üst denetleyici için bir işaretçi.  
  
 `bEnable`  
 Olay, FALSE - devre dışı bırak olay TRUE - etkinleştirin.  
  
### <a name="remarks"></a>Açıklamalar  
 ValueChanged olay etkinleştirildiğinde, sanal bir yöntem CAnimationController::OnAnimationValueChanged framework çağırır. Bu olayın işlenmesi için CAnimationController türetilen bir sınıfta geçersiz kılmanız gerekir. Animasyon değişkeninin değeri her değiştiğinde bu yöntem çağrılır.  
  
##  <a name="getdefaultvalue"></a>CAnimationVariable::GetDefaultValue  
 Varsayılan değerini döndürür.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon değişkeni varsayılan değeri elde etmek için bu işlevi kullanın. Varsayılan değer Oluşturucusu veya SetDefaultValue yöntemi tarafından ayarlanabilir.  
  
##  <a name="getparentanimationobject"></a>CAnimationVariable::GetParentAnimationObject  
 Üst öğesini döndürür animasyon nesnesi.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi üst animasyon nesnesi, ilişki kuruldu, bulunmazsa null değerini DÖNDÜRÜR.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir üst animasyon nesne (kapsayıcı) için bir işaretçi almak için çağrılabilir.  
  
##  <a name="getvalue"></a>CAnimationVariable::GetValue  
 Animasyon değişkenin geçerli değeri döndürür.  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblValue`  
 Animasyon değişkenin geçerli değeri.  
  
 `nValue`  
 Animasyon değişkenin geçerli değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK değeri başarıyla alındı veya arka plandaki animasyon değişkeni oluşturulmadı. Aksi takdirde HRESULT hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, geçerli animasyon değişkenin değerini almak için çağrılabilir. COM nesnesini oluşturulmadığında, dblValue işlevi döndüğünde bir varsayılan değeri içerir.  
  
##  <a name="getvariable"></a>CAnimationVariable::GetVariable  
 Bir işaretçi IUIAnimationVariable COM nesnesi döndürür.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir işaretçi IUIAnimationVariable COM nesnesi ya da animasyon değişkeni oluşturulmadı veya oluşturulamaz yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 IUIAnimationVariable COM nesnesini erişmek ve gerekirse yöntemlerinden doğrudan çağırmak için bu işlevi kullanın.  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationVariable::m_bAutodestroyTransitions  
 İlgili geçiş nesneleri silinmesi gerekip gerekmediğini belirtir.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçişleri iç listeden kaldırılmakta olan zaman geçiş nesnelerinin zorla silinmesini true bu değere ayarlayın. Bu değeri FALSE ise geçişleri uygulama çağırarak silinmesi gerekir. Bir animasyon zamanlanmış sonra geçişleri listesini her zaman temizlenir. Varsayılan değer FALSE olur.  
  
##  <a name="m_dbldefaultvalue"></a>CAnimationVariable::m_dblDefaultValue  
 İçin IUIAnimationVariable yayılır varsayılan değeri belirtir.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>CAnimationVariable::m_lstTransitions  
 Bu animasyon değişken animasyon geçişleri listesini içerir.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>CAnimationVariable::m_pParentObject  
 Bu animasyon değişken yalıtan bir animasyon nesne için bir işaretçi.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>CAnimationVariable::m_variable  
 IUIAnimationVariable COM nesnesi için bir işaretçi depolar. COM Nesne henüz oluşturulmamış veya oluşturma başarısız olursa NULL.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>CAnimationVariable::SetDefaultValue  
 Varsayılan değer ayarlar ve IUIAnimationVariable COM nesnesi serbest bırakır.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblDefaultValue`  
 Yeni varsayılan değer belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan değer sıfırlamak için bu yöntemi kullanın. Animasyon değişkeni yeniden oluşturulduğunda bu yöntem iç IUIAnimationVariable COM nesnesi, bu nedenle serbest bırakır, yeni varsayılan değer COM nesnesini alır. Varsayılan değer, animasyonun değişkeni temsil eden COM nesnesi oluşturulmadı veya değişkeni değil animasyonlu GetValue tarafından döndürülür.  
  
##  <a name="setparentanimationobject"></a>CAnimationVariable::SetParentAnimationObject  
 Bir animasyon değişkeni ve bir animasyon nesne arasındaki ilişkiyi ayarlar.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentObject`  
 Bu değişkeni içeren bir animasyon nesne için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir animasyon değişkeni ve onu yalıtan bir animasyon nesne arasında birebir ilişki kurmak için dahili olarak çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
