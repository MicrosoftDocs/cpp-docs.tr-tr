---
title: "Dize Düzenleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.string.F1
dev_langs:
- C++
helpviewer_keywords:
- String editor
- string tables
- string tables, String editor
- string editing
- string editing, string tables
- resource editors, String editor
- strings [C++], editing
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f0d0f368ec82e46a72977b574b1632bf1d9d6d84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="string-editor"></a>Dize Düzenleyicisi
Bir dize tablo kimlikleri, değerler ve uygulamanızın tüm dizeleri için resim yazıları listesini içeren bir Windows kaynaktır. Örneğin, durum çubuğu istemleri dize tabloda bulunur.  
  
 Bir uygulama geliştirirken, birkaç dize tabloları olabilir — her bir dil veya koşul için bir tane. Ancak, yürütülebilir bir modülü yalnızca bir dize tablosu vardır. Farklı DLL'lere tabloları yerleştirirseniz çalışan bir uygulama çeşitli dize tablolara başvuruda bulunabilir.  
  
 Dize tabloları uygulamanız farklı dillere yerelleştirme kolay hale getirir. Bir dize tabloda tüm dizeleri varsa dizeleri (ve diğer kaynaklar) kaynak kodunu değiştirmeden çevirerek uygulama yerelleştirebilirsiniz. Bu elle bulma ve kaynak dosyaları çeşitli dizelerde değiştirme daha genellikle daha iyi bir şeydir.  
  
 Dize Düzenleyicisi'ni kullanarak şunları yapabilirsiniz:  
  
-   [Bir veya daha fazla Ara](../windows/finding-a-string.md).  
  
-   Hızlı bir şekilde [yeni girdileri eklemek](../windows/adding-or-deleting-a-string.md) dize tabloya.  
  
-   [Bir dizeyi bir kaynak dosyasından diğerine taşıma](../windows/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [Yerinde kimliği, değer ve resim yazısı özelliklerini düzenleme kullanmak](../windows/changing-the-properties-of-a-string.md) ve hemen değişiklikleri görüntüleyin.  
  
-   [Birden çok dizenin resim yazısı özelliğini değiştirme](../windows/changing-the-caption-property-of-multiple-strings.md)  
  
-   [Dizeye biçimlendirme veya özel karakterler ekleme](../windows/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows boş dize tabloları oluşturulmasına izin vermiyor. Bir dize tablosu ile hiçbir girdi oluşturursanız, kaynak dosyasını kaydettiğinizde, otomatik olarak silinir.  
  
 Kaynakları yönetilen projelere (olanlar ortak dil çalışma zamanı hedef) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynakları dizeleri özelliklerine atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows Formları yerelleştirme](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme kaynaklarını kullanan](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Dizeleri](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [Dizeler hakkında](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)

