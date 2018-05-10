---
title: Ekleyerek veya silerek bir dize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], adding to string tables
- string tables, deleting strings
- strings [C++], deleting in string tables
- string tables, adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e15e29c99dba89ef29ba5b909c62f819bedf63f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="adding-or-deleting-a-string"></a>Dize Ekleme veya Silme
Dize Düzenleyicisi'ni kullanarak dize tablosuna yeni giriş kolayca ekleyebilirsiniz. Yeni dizeler tablonun sonuna yerleştirilir ve bir sonraki kullanılabilir tanımlayıcıyı verilir. Sonra kimlik, değer veya resim yazısı özelliklerinde düzenleyebilirsiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window) gerektiğinde.  
  
 Dize Düzenleyicisi'ni, zaten kullanımda olan bir ID'yi kullanmayın emin olur. Bir kimliği zaten kullanımda seçerseniz, Dize Düzenleyicisi'ni size bildirir ve bir genel benzersiz kimlik, örneğin IDS_STRING58113 atayın.  
  
### <a name="to-add-a-string-table-entry"></a>Bir dize tablo girişi eklemek için  
  
1.  Dize tablosu simgesini çift tıklatarak açın [kaynak görünümü](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dize tablo içinde sağ tıklatın ve seçin **yeni bir dize** kısayol menüsünden.  
  
3.  İçinde **dize** Düzenleyicisi, select bir **kimliği** kimliği aşağı açılan listesinden veya türü kimliği doğrudan yerleştir.  
  
4.  Düzen **değeri**gerekirse,.  
  
5.  İçin bir giriş türü **resim yazısı**.  
  
    > [!NOTE]
    >  Null dizeler Windows dize tablolarında izin verilmez. Giriş dizesi tablonun boş bir dize oluşturursanız, "Lütfen girin bir dize için bu tablo girişi." için soran bir ileti alırsınız  
  
### <a name="to-delete-a-string-table-entry"></a>Bir dize tablo girişi silmek için  
  
1.  Silmek istediğiniz girişi seçin.  
  
2.  Üzerinde **Düzenle** menüsünde tıklatın **silmek**.  
  
 \- veya -  
  
-   Silin ve seçmek istediğiniz dize sağ **silmek** kısayol menüsünden.  
  
 \- veya -  
  
-   Tuşuna **silmek** anahtarı.  
  
 Kaynakları yönetilen projelere (olanlar ortak dil çalışma zamanı hedef) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynakları dizeleri özelliklerine atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows Formları yerelleştirme](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme kaynaklarını kullanan](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize Düzenleyicisi](../windows/string-editor.md)   

