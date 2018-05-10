---
title: vi_progid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 687a8a70d7f0a5381160a6515c80f6940cc0a434
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="viprogid"></a>vi_progid
Sürüm bağımsız form ProgID belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Adı*  
 Nesnesini temsil eden sürüm bağımsız ProgID.  
  
 ProgID COM/ActiveX nesneleri tanımlamak için kullanılan sınıf tanımlayıcısı (CLSID) okunabilir bir sürümü var.  
  
## <a name="remarks"></a>Açıklamalar  
 **Vi_progid** C++ öznitelik bir COM nesnesi için sürüm bağımsız bir ProgID belirtmenize olanak sağlar. Formun bir ProgID sahip *name1.name2.version*. Sürüm bağımsız bir ProgID sahip olmayan bir *sürüm*. Her ikisi de belirlemek mümkündür **ProgID** ve **vi_progid** bir coclass'ı öznitelikleri. Belirtmezseniz, **vi_progid**, sürüm bağımsız ProgID tarafından belirtilen değerdir [ProgID](../windows/progid.md) özniteliği.  
  
 **vi_progid** gelir **coclass** belirtirseniz, diğer bir deyişle, öznitelik **vi_progid**, belirtme olarak aynı şeydir **coclass'ı** ve **vi_progid** öznitelikleri.  
  
 **Vi_progid** özniteliği belirtilen adla otomatik olarak kaydedilmesi için bir sınıf neden olur. Oluşturulan .idl dosya ProgID değeri görüntülenmez.  
  
 ATL projelerinde varsa [coclass](../windows/coclass.md) özniteliği de mevcut, belirtilen ProgID tarafından kullanılan **GetVersionIndependentProgID** işlevi (tarafından eklenen **coclass'ı** özniteliği).  
  
## <a name="example"></a>Örnek  
 Bkz: [coclass](../windows/coclass.md) bir örnek kullanımı, örneğin **vi_progid**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [ProgID anahtarı](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
