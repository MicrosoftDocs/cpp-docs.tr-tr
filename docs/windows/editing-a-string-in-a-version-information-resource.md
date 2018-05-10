---
title: Sürüm bilgileri kaynağında dizesinde düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80795f912ab41809b19e77bd33f56243541d4de1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="editing-a-string-in-a-version-information-resource"></a>Sürüm Bilgileri Kaynağında Dize Düzenleme
### <a name="to-edit-a-string-in-a-version-information-resource"></a>Sürüm bilgileri kaynağında dizesinde düzenlemek için  
  
1.  Öğeyi kez düzenlemeye başlamak için daha sonra tekrar seçmek için tıklatın. Sürüm bilgileri tablosundaki doğrudan ya da buna değişiklik [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Yaptığınız değişiklikler, her iki yerde de yansıtılır.  
  
     **Not** düzenlerken **FILEFLAGS** anahtar sürüm bilgileri Düzenleyicisi, siz ayarlanamaz fark edeceksiniz **hata ayıklama**, **özel yapı**, veya **Özel yapı** .rc dosyaları (Özellikler penceresinde) özellikleri:  
  
    -   Sürüm bilgileri Düzenleyicisi kümeleri **hata ayıklama** #ifdef kaynak kodda özelliğiyle temel alarak **_DEBUG** bayrağı oluşturun.  
  
    -   Varsa **özel yapı** anahtara sahip bir **değeri** karşılık gelen sürüm bilgilerini tablo **özel yapı** özelliği (özellik penceresi) için**FILEFLAGS** anahtar olacaktır **doğru**. Varsa **değeri** olan özelliği boş olacaktır **False**. Benzer şekilde, **özel yapı** için (sürüm bilgileri tablosunda) anahtar bağlı **özel yapı** özelliği için **FILEFLAGS** anahtarı.  
  
 Anahtar veya değer sütun başlıkları tıklatarak dize blok bilgi dizisini sıralayabilirsiniz. Bu başlıkları bilgileri seçili sıra içine otomatik olarak yeniden düzenleyin.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sürüm bilgileri Düzenleyicisi](../windows/version-information-editor.md)   
 [Sürüm bilgileri (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

