---
title: Kaynak Dosyalar (C++)
ms.date: 05/14/2019
helpviewer_keywords:
- resource files
- resources [C++]
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
ms.openlocfilehash: 20e57aa51cff8c4e3392c313645468387c2a4244
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707398"
---
# <a name="resource-files-c"></a>Kaynak Dosyalar (C++)

Bilgi sağlamak için kullanıcı arabirimi öğeleri kaynaklardır. Bit eşlemler, simgeler, araç çubukları ve İmleçler tüm kaynaklardır. Bazı kaynaklar, veri iletişim kutusuna girerek veya bir menüden gibi bir eylem gerçekleştirebilirsiniz.

 Daha fazla bilgi için [kaynaklarıyla çalışmaya](../../windows/working-with-resource-files.md).

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*PROJNAME*.rc|*PROJNAME*|Kaynak dosyaları|Proje için kaynak betik dosyası. Kaynak betik dosyası, proje ve proje için (örneğin, araç çubukları, iletişim kutuları veya HTML) seçilen destek türüne bağlı olarak aşağıdakileri içerir:<br /><br />-Varsayılan menü tanımı.<br />-Tablolar Hızlandırıcı ve dize.<br />-Varsayılan **hakkında** iletişim kutusu.<br />-Başka bir iletişim kutusu.<br />-Simge dosyası (res\\*Projname*.ico).<br />-Sürüm bilgisi.<br />-Bit eşlemler.<br />-Araç çubuğu.<br />-HTML dosyaları.<br /><br /> Kaynak dosyası ' % s'dosyası Afxres.rc standart Microsoft Foundation Class kaynakları içerir.|
|Kaynak.h|*PROJNAME*|Üstbilgi Dosyaları|Proje tarafından kullanılan kaynakları için tanımları içeren kaynak üst bilgi dosyası.|
|*PROJNAME*.rc2|*PROJNAME*\res|Kaynak dosyaları|Proje tarafından kullanılan ek kaynaklar içeren betik dosyası. Projenin .rc dosyasında .rc2 dosyayı içerebilir.<br /><br /> Birkaç farklı proje tarafından kullanılan kaynakları dahil etmek için kullanışlı bir .rc2 dosyasıdır. Farklı projelerde aynı kaynakları birkaç kez oluşturmak yerine, bunları bir .rc2 dosyaya yerleştirin ve ana .rc dosyasına .rc2 dosyasını dahil edin.|
|*PROJNAME*.def|*PROJNAME*|Kaynak dosyaları|Modül tanım dosyası için bir DLL projesi. Bir denetim için ad ve açıklama denetimin yanı sıra, çalışma zamanı yığın boyutu sağlar.|
|*PROJNAME*.ico|*PROJNAME*\res|Kaynak Dosyalar|Proje veya denetim için simge dosyası. Uygulama küçültüldüğünde bile bu simge görünür. Uygulamanın kullanılır **hakkında** kutusu. Varsayılan olarak, MFC MFC simgesini görüntüler ve ATL ATL simgesi sağlar.|
|*PROJNAME*Doc.ico|*PROJNAME*\res|Kaynak Dosyalar|Belge/görünüm mimarisi desteği içeren bir MFC projesi için simge dosyası.|
|ToolBar.bmp|*PROJNAME*\res|Kaynak Dosyalar|Uygulamanın veya denetimin bir araç veya palet temsil eden bir bit eşlem dosyası. Bu bit eşlem projenin kaynak dosyasına dahil edilir. İlk araç çubuğu ve durum çubuğu içinde yapılandırılan **CMainFrame** sınıfı.|
|Ribbon.mfcribbon ms|*PROJNAME*\res|Kaynak Dosyalar|Şerit düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren kaynak dosya. Daha fazla bilgi için [Şerit Tasarımcısı (MFC)](../../mfc/ribbon-designer-mfc.md).|

## <a name="see-also"></a>Ayrıca bkz.

[Oluşturulan türleri için Visual Studio dosya C++ projeleri](file-types-created-for-visual-cpp-projects.md)
