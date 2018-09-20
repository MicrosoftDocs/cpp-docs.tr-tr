---
title: Sınıf ekleme (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2ef8ae3e7620efb74099287dcda29210545d2e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420549"
---
# <a name="adding-a-class-visual-c"></a>Sınıf Ekleme (Visual C++)

Visual C++ projesinde bir sınıf eklemek için **Çözüm Gezgini**, projeye sağ tıklayın, **Ekle**ve ardından **sınıfı**. Bu açılır [sınıfı iletişim kutusunu](../ide/add-class-dialog-box.md) iletişim kutusu.

Bir sınıf eklediğinizde, MFC veya ATL içinde zaten mevcut sınıflardan farklı bir ad belirtmelisiniz Her iki Kitaplığı'nda zaten bir ad belirtirseniz, IDE bir hata iletisi gösterir.

Adlandırma projeniz var olan bir adı kullanmak gerektiriyorsa, C++ büyük/küçük harfe duyarlıdır çünkü daha sonra yalnızca büyük/küçük harf, bir veya daha fazla ad değiştirebilirsiniz. Örneğin, bir sınıf adı olamaz ancak `CDocument`, ad verebilirsiniz `cdocument`.

## <a name="what-kind-of-class-do-you-want-to-add"></a>Ne tür bir sınıf eklemek istiyor musunuz?

İçinde **sınıfı Ekle** genişlettikten iletişim kutusu, **Visual C++** düğümü sol bölmedeki yüklü şablonlar birkaç gruplandırmaları görüntülenir. Grupları dahil **CLR**, **ATL**, **MFC**, ve **C++**. Bir grubu seçtiğinizde, o grup içindeki kullanılabilir şablonların listesini Orta bölmede görüntülenir. Her şablon, bir sınıf için gerekli olan kaynak kodu ve dosyaları içerir.

Yeni bir sınıf oluşturmak için Orta bölmede bir şablon seçin, sınıf için bir ad yazın **adı** ve'ı tıklatın **Ekle**. Bu açılır **sınıf Ekleme Sihirbazı'nı** sınıfı için seçenekleri belirtebilirsiniz.

- MFC sınıfları oluşturma hakkında daha fazla bilgi için bkz. [MFC sınıfı](../mfc/reference/adding-an-mfc-class.md).

- ATL sınıfları oluşturma hakkında daha fazla bilgi için bkz. [ATL Basit Nesne](../atl/reference/adding-an-atl-simple-object.md).

> [!NOTE]
>  Şablon **MFC ATL desteği Ekle** bir sınıf oluşturmaz, ancak bunun yerine projeyi ATL kullanacak şekilde yapılandırır Daha fazla bilgi için [MFC projesinde ATL desteği](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

MFC, ATL veya CLR kullanmayan C++ sınıfı yapma **C++ sınıfı** şablonunda **C++** Grup yüklü şablonlar. Daha fazla bilgi için [genel C++ sınıfı ekleme](../ide/adding-a-generic-cpp-class.md).

İki tür form tabanlı C++ sınıfları kullanılabilir. Birinci [CFormView sınıfı](../mfc/reference/cformview-class.md) MFC sınıfı oluşturur. İkinci bir CLR Windows Forms sınıf oluşturur.

## <a name="see-also"></a>Ayrıca Bkz.

[Form Tabanlı MFC Uygulaması Oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md)<br>
[Sınıf Ekle İletişim Kutusu](../ide/add-class-dialog-box.md)<br>
[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)