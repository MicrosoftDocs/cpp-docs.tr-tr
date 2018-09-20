---
title: Kullanıcıların çıkamayacağı iletişim kutusu (C++) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], creating
- modal dialog boxes [C++], logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5abae461b4298d8a6300f5d7ad9f3e162a5b21c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447394"
---
# <a name="creating-a-dialog-box-c-that-users-cannot-exit"></a>Çıkamayacağı iletişim kutusu (C++), kullanıcıları oluşturma

Bir kullanıcı çıkamayacağı bir çalışma zamanı iletişim kutusu oluşturabilirsiniz. Bu tür bir iletişim kutusu, oturum açma ve uygulama veya belge kilit için kullanışlıdır.

### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>Bir kullanıcı çıkamayacağı iletişim kutusu oluşturmak için

1. İçinde **özellikleri** iletişim kutusu için bölmesinde **sistem menüsü** özelliğini **false**.

   Bu iletişim kutusunu sistem menüsü devre dışı bırakır ve **Kapat** düğmesi.

2. İletişim kutusu formda Sil **iptal** ve **Tamam** düğmeleri.

   Çalışma zamanında, bir kullanıcı bu özelliklere sahip bir modal iletişim kutusu çıkamayacağı.

İletişim kutusunun bu tür bir testi etkinleştirmek için test iletişim kutusu işlevi zaman algılar **Esc** basıldığında. (**Esc** de VK_ESCAPE sanal anahtar denir.) Nasıl iletişim kutusunda çalışma zamanında davranacak şekilde tasarlanmış ne olursa olsun, bu test modunda tuşlarına basarak sonlandırabilirsiniz **Esc**.

> [!NOTE]
> MFC uygulamaları için kullanıcıların çıkamayacağı, bir iletişim kutusu oluşturmak için varsayılan davranışı geçersiz kılmanız gerekir `OnOK` ve `OnCancel` ilişkili düğmeleri silseniz bile iletişim kutusunun hala tuşlarına basarak kapatılabilir çünkü  **Girin** veya **Esc**.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kaynak Oluşturma](../windows/how-to-create-a-resource.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)