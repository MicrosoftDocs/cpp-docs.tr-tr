---
title: "Nesne eşleme makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs: C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8c1547f4d78c599ef0e272e8e2e881430c72ced1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="object-map-macros"></a>Nesne eşleme makroları
Bu makroları nesne eşlemeleri ve girişleri tanımlayın.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Nesne eşlemeye girilecek bir sınıf nesnesinin metin açıklaması belirtmenize olanak tanır.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|ATL nesneyi nesne eşlemeye girer, kayıt defterini güncelleştirir ve nesne örneğini oluşturur.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Nesne kayıtlı ve başlatılmış olduğundan belirtmenize olanak sağlar, ancak bunu dışarıdan aracılığıyla oluşturulabilmelidir değil `CoCreateInstance`.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 Sınıf nesnesi için bir metin açıklama belirtmenize olanak tanır.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Sınıf nesnenin açıklaması.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL bu açıklama nesne eşlemesi üzerinden girer [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) makrosu.  
  
 `DECLARE_OBJECT_DESCRIPTION`arabirimini uygulayan bir `GetObjectDescription` geçersiz kılmak için kullanabileceğiniz işlevi [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) yöntemi.  

  
 `GetObjectDescription` İşlevi çağrıldığında **IComponentRegistrar::GetComponents**. **IComponentRegistrar** kaydolun ve DLL bileşenleri tek tek kaydı olanak tanıyan bir Otomasyon arabirimdir. ATL Proje Sihirbazı'yla bir bileşen Kaydedicisi nesne oluşturduğunuzda, sihirbaz otomatik olarak uygulaması **IComponentRegistrar** arabirimi. **IComponentRegistrar** genellikle Microsoft işlem sunucusu tarafından kullanılır.  
  
 ATL Proje Sihirbazı hakkında daha fazla bilgi için bkz: [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO  
 ATL nesneyi nesne eşlemeye girer, kayıt defterini güncelleştirir ve nesne örneğini oluşturur.  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 [in] Adlı C++ sınıfı tarafından uygulanan bir COM sınıfı CLSID `class`.  
  
 `class`  
 [in] Tarafından temsil edilen COM sınıfı uygulama C++ sınıfın adını `clsid`.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne giriş makroları kayıt, başlatma ve bir sınıf oluşturulması için destek sağlamak için projeyi genel kapsamda yerleştirilir.  
  
 `OBJECT_ENTRY_AUTO`işlev işaretçileri oluşturan ve sınıf üreticisi creator sınıf girer `CreateInstance` işlevleri otomatik olarak oluşturulan ATL nesne eşlemesi içine bu nesne için. Zaman [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) olduğu adlı nesne eşlemesindeki her nesne için sistem kayıt defterini güncelleştirir.  

  
 Aşağıdaki tabloda, bu makro ikinci parametre olarak belirtilen sınıftan nesne eşlemesine eklenen bilgiler nasıl elde açıklanmaktadır.  
  
|Bilgi için|Alınan|  
|---------------------|-------------------|  
|COM kayıt|[Kayıt defteri makroları](../../atl/reference/registry-macros.md)|  
|Sınıf fabrikası oluşturma|[Sınıf Fabrika makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Örnek oluşturma|[Toplama makroları](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Bileşen kategori kaydı|[Kategori makroları](../../atl/reference/category-macros.md)|  
|Sınıf düzeyi başlatma ve temizleme|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO  
 Nesne kayıtlı ve başlatılmış olduğundan belirtmenize olanak sağlar, ancak bunu dışarıdan aracılığıyla oluşturulabilmelidir değil `CoCreateInstance`.  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 [in] Adlı C++ sınıfı tarafından uygulanan bir COM sınıfı CLSID `class`.  
  
 `class`  
 [in] Tarafından temsil edilen COM sınıfı uygulama C++ sınıfın adını `clsid`.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne giriş makroları kayıt, başlatma ve bir sınıf oluşturulması için destek sağlamak için projeyi genel kapsamda yerleştirilir.  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`bir nesne kayıtlı ve başlatılmış olduğundan belirtmenizi sağlar (bkz [OBJECT_ENTRY_AUTO](#object_entry_auto) daha fazla bilgi için), ancak bunu aracılığıyla oluşturulabilmelidir değil `CoCreateInstance`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
