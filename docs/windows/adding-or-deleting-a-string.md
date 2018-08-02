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
ms.openlocfilehash: 90a470aa5bb1b24ab2fe549f098a83c29e5d0828
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464155"
---
# <a name="adding-or-deleting-a-string"></a>Dize Ekleme veya Silme
Dize Düzenleyicisi'ni kullanarak dize tablosuna yeni girişler kolayca ekleyebilirsiniz. Yeni dizeler tablonun sonuna yerleştirilir ve sonraki kullanılabilir tanımlayıcı verilir. Ardından kimliği, değer veya resim yazısı özelliklerinde düzenleyebileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) gerektiğinde.  
  
 Dize Düzenleyicisi'ni zaten kullanımda bir kimliği kullanmayın emin olur. Bir kimliği zaten kullanımda seçerseniz, Dize Düzenleyicisi bunu size bildirir ve ardından genel benzersiz bir kimliği olan örneğin IDS_STRING58113 atayın.  
  
### <a name="to-add-a-string-table-entry"></a>Dize tablo girdisi eklemek için  
  
1.  Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dize tablosu içinde sağ tıklatın ve seçin **yeni dize** kısayol menüsünden.  
  
3.  İçinde **dize** Düzenleyicisi'ni seçin bir **kimliği** kimliği aşağı açılan listesinden veya türü kimliği ile doğrudan bir yerde.  
  
4.  Düzen **değer**, gerekirse.  
  
5.  İçin bir giriş türü **açıklamalı alt yazı**.  
  
    > [!NOTE]
    >  Null dizeler Windows dize tablolarında izin verilmez. Boş bir dize olan dize tablosunda bir giriş oluşturmak, "Lütfen gir bir dize Bu tablo girişi için" için soran bir ileti alırsınız.  
  
### <a name="to-delete-a-string-table-entry"></a>Dize tablosu girişi silmek için  
  
1.  Silmek istediğiniz girişini seçin.  
  
2.  Üzerinde **Düzenle** menüsünde tıklatın **Sil**.  
  
 \- veya -  
  
-   Sağ tıklayın ve silmek istediğiniz dizeyi **Sil** kısayol menüsünden.  
  
 \- veya -  
  
-   Tuşuna **Sil** anahtarı.  
  
 Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme için kaynakların kullanarak](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize Düzenleyicisi](../windows/string-editor.md)   