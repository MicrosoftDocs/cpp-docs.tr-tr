---
title: Dizeyi bir kaynak dosyasından başka bir (C++) taşıma.
ms.date: 11/04/2016
helpviewer_keywords:
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
ms.openlocfilehash: e89a0d44dc824c72710f8a047a18771ba8da492b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649820"
---
# <a name="moving-a-string-from-one-resource-file-to-another-c"></a>Dizeyi bir kaynak dosyasından başka bir (C++) taşıma.

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak betik dosyasını diğerine taşımak için

1. Dize tabloları içinde her iki .rc dosyası açın. (Daha fazla bilgi için [kaynaklar içinde bir kaynak betik dosyası dışında sonuna bir proje görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Sağ tıklayın, istediğiniz Taşı ve dize **Kes** kısayol menüsünden.

3. Hedef imleci **Dize Düzenleyicisi** penceresi.

4. Dize taşımak istediğiniz .rc dosyasına sağ tıklayın ve seçin **Yapıştır** kısayol menüsünden.

   > [!NOTE]
   > Varsa **kimliği** veya **değer** ile varolan taşınan dize çakışmalar **kimliği** veya **değer** hedef dosyasında ya da **Kimliği** veya **değer** taşınan dize değişiklikleri. Bir dize ile aynı varsa **kimliği**, **kimliği** taşınan dize değişiklikleri. Bir dize ile aynı varsa **değer**, **değer** taşınan dize değişiklikleri.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio)