---
title: "CAnimationValue sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
dev_langs:
- C++
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b37801619fae84519dde000c922d34c4b9e1509
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimationvalue-class"></a>CAnimationValue sınıfı
Bir değere sahip animasyon nesnesinin işlevselliğini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](#canimationvalue)|Fazla Yüklendi. CAnimationValue nesnesi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](#addtransition)|Bir değere uygulanacak bir geçiş ekler.|  
|[CAnimationValue::GetValue](#getvalue)|Fazla Yüklendi. Geçerli değeri alır.|  
|[CAnimationValue::GetVariable](#getvariable)|Kapsüllenmiş animasyon değişkenine erişim sağlar.|  
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Varsayılan değer ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkeni bir liste olarak geçirir. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationValue::operator çift](#operator_double)|CAnimationValue ve çift arasında dönüştürme sağlar.|  
|[CAnimationValue::operator Int32](#operator_int32)|CAnimationValue ve Int32 arasında dönüştürme sağlar.|  
|[CAnimationValue::operator =](#operator_eq)|Fazla Yüklendi. Bir Int32 değeri için CAnimationValue atar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationValue::m_value](#m_value)|Animasyon değeri temsil eden kapsüllenmiş animasyon değişken.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationValue sınıf tek bir CAnimationVariable nesne yalıtır ve uygulamaları tek bir animasyonlu değer temsil edebilir. Animasyonlu saydamlık (yavaşça etkisi) açı için (nesneleri döndürmek için), örneğin, bu sınıfın kullanabilirsiniz veya tek bir animasyonlu değere bağlı olarak bir animasyon oluşturmanız gerektiğinde herhangi diğer durumu. Bu sınıf uygulamada kullanmak için yalnızca bu sınıfın bir nesnesi örneği, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve değere uygulanacak AddTransition her geçiş için çağırın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationValue`
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationValue::AddTransition  
 Bir değere uygulanacak bir geçiş ekler.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTransition`  
 Geçiş nesnesine bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir geçiş bir animasyon değişkenine uygulanacak geçişleri iç listesine eklemek için bu işlevini çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listede depolanmış. Geçişleri (belirli bir değeri bir film şeridi eklenebilir) uygulanır CAnimationController::AnimateGroup çağırdığınızda.  
  
##  <a name="canimationvalue"></a>CAnimationValue::CAnimationValue  
 CAnimationValue nesnesi oluşturur.  
  
```  
CAnimationValue();

 
CAnimationValue(
    DOUBLE dblDefaultValue,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblDefaultValue`  
 Varsayılan bir değer belirtir.  
  
 `nGroupID`  
 Grup kimliğini belirtir.  
  
 `nObjectID`  
 Nesne kimliğini belirtir.  
  
 `dwUserData`  
 Kullanıcı tanımlı veri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan özelliklerine sahip CAnimationValue nesnesi oluşturur: varsayılan değer, grup kimliği ve nesne kimliği 0 olarak ayarlanmış.  
  
##  <a name="getanimationvariablelist"></a>CAnimationValue::GetAnimationVariableList  
 Kapsüllenmiş animasyon değişkeni bir liste olarak geçirir.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parametreler  
 `lst`  
 İşlevi döndüğünde CAnimationVariable animasyonlu değerini gösteren bir işaretçi içeriyor.  
  
##  <a name="getvalue"></a>CAnimationValue::GetValue  
 Geçerli değeri alır.  
  
```  
BOOL GetValue(DOUBLE& dblValue);  
BOOL GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblValue`  
 Çıktı. İşlevi döndüğünde animasyon değişkenin geçerli bir değer içerir.  
  
 `nValue`  
 Çıktı. İşlevi döndüğünde animasyon değişkenin geçerli bir değer içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli değer başarıyla alındığında TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli değer almak için bu işlevini çağırın. Bu uygulama kapsüllenmiş COM nesnesi çağırır ve çağrısı başarısız olursa, bu yöntem Oluşturucusu veya SetDefaultValue önceden ayarlanmış varsayılan değerini döndürür.  
  
##  <a name="getvariable"></a>CAnimationValue::GetVariable  
 Kapsüllenmiş animasyon değişkenine erişim sağlar.  
  
```  
CAnimationVariable& GetVariable();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kapsüllenmiş animasyon değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsüllenmiş animasyon değişkeni erişmek için bu yöntemi kullanın. CAnimationVariable animasyon değişkeni oluşturulmadı, işaretçisi NULL olabilir, temel alınan IUIAnimationVariable nesnesini erişin.  
  
##  <a name="m_value"></a>CAnimationValue::m_value  
 Animasyon değeri temsil eden kapsüllenmiş animasyon değişken.  
  
```  
CAnimationVariable m_value;  
```  
  
##  <a name="operator_double"></a>CAnimationValue::operator çift  
 CAnimationValue ve çift arasında dönüştürme sağlar.  
  
```  
operator DOUBLE();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon değeri geçerli değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationValue ve çift arasında dönüştürme sağlar. Bu yöntem, dahili olarak GetValue çağırır ve hatalar için denetlemez. GetValue başarısız olursa, döndürülen değer Oluşturucusu veya SetDefaultValue önceden ayarlanmış bir varsayılan değeri içerir.  
  
##  <a name="operator_int32"></a>CAnimationValue::operator Int32  
 CAnimationValue ve Int32 arasında dönüştürme sağlar.  
  
```  
operator INT32();
```   
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon değeri tamsayı olarak geçerli değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationValue ve Int32 arasında dönüştürme sağlar. Bu yöntem, dahili olarak GetValue çağırır ve hatalar için denetlemez. GetValue başarısız olursa, döndürülen değer Oluşturucusu veya SetDefaultValue önceden ayarlanmış bir varsayılan değeri içerir.  
  
##  <a name="operator_eq"></a>CAnimationValue::operator =  
 DOUBLE değeri için CAnimationValue atar.  
  
```  
void operator=(DOUBLE dblVal);  
void operator=(INT32 nVal);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblVal`  
 Animasyon değerine atanacak değeri belirtir.  
  
 `nVal`  
 Animasyon değerine atanacak değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 DOUBLE değeri için CAnimationValue atar. Bu değer, kapsüllenmiş animasyon değişken için bir varsayılan değer olarak ayarlanır. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesneye abone, bu olayları yeniden etkinleştirmeniz gerekir.  
  
##  <a name="setdefaultvalue"></a>CAnimationValue::SetDefaultValue  
 Varsayılan değer ayarlar.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `dblDefaultValue`  
 Varsayılan değer belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan bir değer ayarlamak için bu yöntemi kullanın. Varsayılan değer olduğunda animasyon başlatılmadı ve/veya COM nesnesini oluşturulmadı uygulamaya döndürülür. İçinde CAnimationVarible kapsüllenmiş olan COM nesnesini zaten oluşturulmuşsa, bu yöntem yeniden oluşturur, bu nedenle EnableValueChanged/EnableIntegerValueChanged yöntemleri yeniden başvurmanız gerekebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
