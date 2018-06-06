---
title: IDL öznitelikleri, yöntem Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a7a1e8fe89f64ad5909e7c1415545e3b3d80196
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337775"
---
# <a name="idl-attributes-add-method-wizard"></a>IDL Öznitelikleri, Yöntem Ekleme Sihirbazı
Yöntem Ekleme Sihirbazı'nı bu sayfanın tüm arabirimi tanım dili (IDL) ayarlarını yöntemi belirtmek için kullanın.  
  
 **id**  
 Yöntemi tanımlayan sayısal Kimliğini ayarlar. Bkz: [kimliği](http://msdn.microsoft.com/library/windows/desktop/aa367040) içinde *MIDL başvuru*.  
  
 Bu kutu için özel arabirimleri kullanılamıyor ve MFC dispinterfaces için kullanılamaz.  
  
 **call_as**  
 Bu yerel yöntemini eşlenebilir uzak bir yöntemin adını belirtir. Bkz: [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) içinde *MIDL başvuru*.  
  
 MFC dispinterfaces için kullanılamaz.  
  
 **helpcontext**  
 Bu yöntemi Yardım dosyasında kullanıcı görünümü bilgi sağlayan bir içerik Kimliğini belirtir. Bkz: [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) içinde *MIDL başvuru*.  
  
 MFC dispinterfaces için kullanılamaz.  
  
 **helpstring**  
 Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak, bunu ayarlamak "yöntem *yöntem adı*." Bkz: [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) içinde *MIDL başvuru*.  
  
 MFC dispinterfaces için kullanılamaz.  
  
 **Ek öznitelikler**  
 MFC dispinterfaces için kullanılamaz.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**hidden**|Yöntem var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) içinde *MIDL başvuru*.|  
|**Kaynak**|Yöntemi, üyesi olayları kaynağı olduğunu gösterir. Bkz: [kaynak](http://msdn.microsoft.com/library/windows/desktop/aa367166) içinde *MIDL başvuru*.|  
|`local`|MIDL derleyici yöntemi uzak olmadığını belirtir. Bkz: [yerel](http://msdn.microsoft.com/library/windows/desktop/aa367071) içinde *MIDL başvuru*.|  
|**restricted**|Yöntem rasgele çağrılamaz belirtir. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) içinde *MIDL başvuru*.|  
|**vararg**|Değişken sayıda bağımsız değişken yöntemi aldığını belirtir. Bunu başarmak için son bağımsız değişken güvenli bir dizi olmalıdır **değişken** kalan tüm bağımsız değişkenler içeren türü. Bkz: [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) içinde *MIDL başvuru*.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yöntem ekleme](../ide/adding-a-method-visual-cpp.md)   
 [Yöntem Ekleme Sihirbazı](../ide/add-method-wizard.md)