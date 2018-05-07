---
title: CAccelerateDecelerateTransition Class1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1dac40e91dd7b0a91c5d76b0d665d075e562267
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition sınıfı
Bir accelerate uygulayan-geçiş hızını düşürün.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Bir geçiş nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Süre hızlandırmaya harcanan süre oranı.|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Süre yavaşlatıcı harcanan süre oranı.|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Geçiş süresi.|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Geçiş işleminin sonunda animasyon değişkeninin değeri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir accelerate sırasında-geçiş hızını düşürün, animasyon değişkeni hızlandırır ve belirli bir değerde bitiş geçiş süresini üzerinden sonra yavaşlar. Ne kadar hızlı değişkeni hızlandırır ve bağımsız olarak, farklı hızlandırma ve yavaşlama oranları belirterek decelerates kontrol edebilirsiniz. İlk hız sıfır hızlandırma oranına değişkeni hızlandırmaya harcadıkları süre kesir olur; benzer şekilde ile yavaşlama oranı. İlk hız sıfır ise, sıfır ve geçiş sonunda ulaşmasını hız arasındaki süre bölümüdür. Hızlandırma oranı ve yavaşlama oranı 1.0 maksimum kadar sum. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işlecini kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Bu COM nesnesinin oluşturulmasını etkisizdir sonra üye değişkenleri değiştirme.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
 Bir geçiş nesnesi oluşturur.  
  
```  
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE accelerationRatio = 0.3,  
    DOUBLE decelerationRatio = 0.3);
```  
  
### <a name="parameters"></a>Parametreler  
 `duration`  
 Geçiş süresi.  
  
 `finalValue`  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
 `accelerationRatio`  
 Süre hızlandırmaya harcanan süre oranı.  
  
 `decelerationRatio`  
 Süre yavaşlatıcı harcanan süre oranı.  
  
##  <a name="create"></a>  CAccelerateDecelerateTransition::Create  
 Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>Parametreler  
`pLibrary`  
 Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](https://msdn.microsoft.com/library/windows/desktop/dd371897), standart geçişleri kitaplığı tanımlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçiş başarılı bir şekilde oluşturulursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio  
 Süre hızlandırmaya harcanan süre oranı.  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio  
 Süre yavaşlatıcı harcanan süre oranı.  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration  
 Geçiş süresi.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue  
 Geçiş işleminin sonunda animasyon değişkeninin değeri.  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
