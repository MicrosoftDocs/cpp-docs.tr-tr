---
title: ProgID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2b2d2168b568c74c5404cc83bab1e5f77570773
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880439"
---
# <a name="progid"></a>progid
Bir COM nesnesi ProgID belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Adı*  
 Nesnesini temsil eden ProgID.  
  
 ProgID COM/ActiveX nesneleri tanımlamak için kullanılan sınıf tanımlayıcısı (CLSID) okunabilir bir sürümü var.  
  
## <a name="remarks"></a>Açıklamalar  
 **ProgID** C++ öznitelik bir COM nesnesi ProgID belirtmenize olanak sağlar. Formun bir ProgID sahip *name1.name2.version*. Belirtmezseniz, bir *sürüm* bir ProgID için varsayılan sürüm 1'dir. Belirtmezseniz, *name1.name2*, varsayılan ad *classname.classname*. Belirtmezseniz, **ProgID** ve belirttiğiniz **vi_progid**, *name1.name2* runbook'undan alınan **vi_progid** ve (bir sonraki sıralı sürüm numarası) eklenir.  
  
 Kullanan bir öznitelik bloğu varsa **ProgID** da kullanmayan `uuid`, derleyici kayıt olup olmadığını kontrol eder bir `uuid` için belirtilen var. **ProgID**. Varsa **ProgID** belirtilmezse, oluşturmak için sürüm (ve bir coclass'ı oluşturuyorsanız coclass'ı adı) kullanılacak bir **ProgID**.  
  
 **ProgID** gelir **coclass** belirtirseniz, diğer bir deyişle, öznitelik **ProgID**, belirtme olarak aynı şeydir **coclass** ve  **ProgID** öznitelikleri.  
  
 **ProgID** özniteliği belirtilen adla otomatik olarak kaydedilmesi için bir sınıf neden olur. Oluşturulan .idl dosya görüntülenmez **ProgID** değeri.  
  
 Bu öznitelik, ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, bu öznitelik ile belirtilen bilgileri kullanılan **GetProgID** tarafından eklenen işlev, **coclass** özniteliği. Daha fazla bilgi için bkz: [coclass](../windows/coclass.md) özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [coclass](../windows/coclass.md) bir örnek kullanım için **ProgID**.  
  
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
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID anahtarı](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
