---
title: Kullanıcıların çıkamayacağı iletişim kutusu oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, creating
- modal dialog boxes, logon screens
- logon screens
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc04c9ccfb0fdc74e57142bf746681411bbba495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33884469"
---
# <a name="creating-a-dialog-box-that-users-cannot-exit"></a>Kullanıcıların Çıkamayacağı İletişim Kutusu Oluşturma
Bir kullanıcı çıkamayacağı bir çalışma zamanı iletişim kutusu oluşturabilirsiniz. Bu tür bir iletişim kutusu için oturum ve uygulama veya belge kilitleri için yararlıdır.  
  
### <a name="to-create-a-dialog-box-that-a-user-cannot-exit"></a>Bir kullanıcı çıkamayacağı iletişim kutusu oluşturmak için  
  
1.  İçinde **özellikleri** kümesi bölmesi iletişim kutusu için **sistem menüsü** özelliğine **false**.  
  
     Bu iletişim kutusunu Sistem menüsünü devre dışı bırakır ve **Kapat** düğmesi.  
  
2.  İletişim kutusu formu silme **iptal** ve **Tamam** düğmeler.  
  
     Çalışma zamanında, bir kullanıcı bu özelliklere sahip bir modal iletişim kutusu çıkamayacağı.  
  
 Bu tür iletişim kutusunun testlerini etkinleştirmek için ESC tuşuna bastığınızda, test iletişim kutusu işlevi algılar. (ESC olarak da bilinen VK_ESCAPE sanal anahtardır.) Nasıl iletişim kutusu çalışma zamanında davranacak şekilde tasarlanmış olsun, bu sınama modunda ESC tuşuna basarak sonlandırabilir.  
  
> [!NOTE]
>  MFC uygulamaları için kullanıcıların çıkamayacağı, bir iletişim kutusu oluşturmak için varsayılan davranışı geçersiz kılmanız gerekir `OnOK` ve `OnCancel` ilişkili düğmeleri silme olsa bile, iletişim kutusu hala ENTER veya ESC tuşuna basarak kapatılabilir olduğundan.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

