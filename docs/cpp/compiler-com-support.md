---
title: "Derleyici COM desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 86caaf78ff105f02e2eabe6637e9e80829f53be0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-com-support"></a>Derleyici COM Desteği
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Visual C++ derleyicisi doğrudan Bileşen Nesne Modeli (COM) tür kitaplıklarının okuyun ve derlemede dahil edilebilir C++ kaynak kodu içine içeriği çevir. Dil uzantıları istemci tarafında programlama COM kolaylaştırmak kullanılabilir.  
  
 Kullanarak [#import önişlemci yönergesi](../preprocessor/hash-import-directive-cpp.md)derleyici bir tür kitaplığı okuyabilir ve COM açıklayan bir C++ üstbilgi dosyası içine arabirimleri olarak dönüştürme sınıfları. Bir dizi `#import` öznitelikler, kullanıcı denetimi elde edilen tür kitaplığı üstbilgi dosyaları için içeriğin için kullanılabilir.  
  
 Kullanabileceğiniz [__declspec](../cpp/declspec.md) genişletilmiş öznitelik [UUID](../cpp/uuid-cpp.md) bir genel benzersiz tanımlayıcı (GUID) bir COM nesnesine atanamadı. Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) bir COM nesnesi ile ilişkili GUID ayıklamak için kullanılabilir. Başka bir `__declspec` özniteliği [özelliği](../cpp/property-cpp.md), belirtmek için kullanılan **almak** ve **ayarlamak** veri üyesi bir COM nesnesi için yöntemleri.  
  
 COM desteği genel işlevler ve sınıfları kümesi desteklemek için sağlanan **değişken** ve `BSTR` türleri, akıllı işaretçiler uygulamak ve tarafından oluşturulan hata nesnesi kapsülleyen `_com_raise_error`:  
  
-   [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)  
  
-   [_bstr_t](../cpp/bstr-t-class.md)  
  
-   [_com_error](../cpp/com-error-class.md)  
  
-   [_com_ptr_t](../cpp/com-ptr-t-class.md)  
  
-   [_variant_t](../cpp/variant-t-class.md)  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)   
 [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)