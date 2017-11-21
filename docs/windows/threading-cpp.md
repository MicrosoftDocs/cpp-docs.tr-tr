---
title: "iş parçacığı oluşturma (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.threading
dev_langs: C++
helpviewer_keywords: threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c85287a590dfa9cf3c931ce358dca8b303f4737a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="threading-c"></a>iş parçacığı oluşturma (C++)
Bir COM nesnesi için iş parçacığı modelini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 ***Model*** (isteğe bağlı)  
 Aşağıdaki iş parçacığı oluşturma modelleri biri:  
  
-   **Grup** (Grup iş parçacığı oluşturma)  
  
-   **dilden bağımsız** (.NET Framework bileşenlerini kullanıcı arabirimi olmadan)  
  
-   **tek** (basit iş parçacığı oluşturma)  
  
-   **Ücretsiz** (iş parçacığı oluşturma boş)  
  
-   **her ikisi de** (Grup ve boş iş parçacığı oluşturma)  
  
 Varsayılan değer **grup**.  
  
## <a name="remarks"></a>Açıklamalar  
 **İş parçacığı oluşturma** C++ öznitelik oluşturulan .idl dosyasında görünmez ancak COM nesnesi uygulamasında kullanılır.  
  
 ATL projelerinde varsa [coclass](../windows/coclass.md) özniteliği varsa, aynı zamanda tarafından belirtilen iş parçacığı modelini *modeli* şablon parametre olarak geçirilen [in uygulamasına](../atl/reference/ccomobjectrootex-class.md) sınıfı , tarafından eklenen **coclass** özniteliği.  
  
 **İş parçacığı oluşturma** özniteliği de erişimi korur bir [event_source](../windows/event-source.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [lisanslı](../windows/licensed.md) bir örnek kullanımı, örneğin **iş parçacığı oluşturma**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Eski kod (Visual C++) için çoklu iş parçacığı desteği](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Dilden bağımsız grupların](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
