---
title: "IDL öznitelikleri, yöntem Ekleme Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.method.idlattrib
dev_langs: C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 583b2c0ec67c4799753fe52d74131e7238b11d46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idl-attributes-add-method-wizard"></a>IDL Öznitelikleri, Yöntem Ekleme Sihirbazı
Yöntem Ekleme Sihirbazı'nı bu sayfanın tüm arabirimi tanım dili (IDL) ayarlarını yöntemi belirtmek için kullanın.  
  
 **Kimliği**  
 Yöntemi tanımlayan sayısal Kimliğini ayarlar. Bkz: [kimliği](http://msdn.microsoft.com/library/windows/desktop/aa367040) içinde *MIDL başvuru*.  
  
 Bu kutu için özel arabirimleri kullanılamıyor ve MFC dispinterfaces için kullanılamaz.  
  
 **call_as**  
 Bu yerel yöntemini eşlenebilir uzak bir yöntemin adını belirtir. Bkz: [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) içinde *MIDL başvuru*.  
  
 MFC dispinterfaces için kullanılamaz.  
  
 **HelpContext**  
 Bu yöntemi Yardım dosyasında kullanıcı görünümü bilgi sağlayan bir içerik Kimliğini belirtir. Bkz: [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) içinde *MIDL başvuru*.  
  
 MFC dispinterfaces için kullanılamaz.  
  
 **HelpString**  
 Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak, bunu ayarlamak "yöntem *yöntem adı*." Bkz: [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) içinde *MIDL başvuru*.  
  
 MFC dispinterfaces için kullanılamaz.  
  
 **Ek öznitelikler**  
 MFC dispinterfaces için kullanılamaz.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**Gizli**|Yöntem var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) içinde *MIDL başvuru*.|  
|**Kaynak**|Yöntemi, üyesi olayları kaynağı olduğunu gösterir. Bkz: [kaynak](http://msdn.microsoft.com/library/windows/desktop/aa367166) içinde *MIDL başvuru*.|  
|`local`|MIDL derleyici yöntemi uzak olmadığını belirtir. Bkz: [yerel](http://msdn.microsoft.com/library/windows/desktop/aa367071) içinde *MIDL başvuru*.|  
|**sınırlı**|Yöntem rasgele çağrılamaz belirtir. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) içinde *MIDL başvuru*.|  
|**Vararg**|Değişken sayıda bağımsız değişken yöntemi aldığını belirtir. Bunu başarmak için son bağımsız değişken güvenli bir dizi olmalıdır **değişken** kalan tüm bağımsız değişkenler içeren türü. Bkz: [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) içinde *MIDL başvuru*.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yöntem ekleme](../ide/adding-a-method-visual-cpp.md)   
 [Yöntem Ekleme Sihirbazı](../ide/add-method-wizard.md)