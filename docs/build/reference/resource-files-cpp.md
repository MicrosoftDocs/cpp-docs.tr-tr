---
description: 'Daha fazla bilgi edinin: proje kaynak dosyaları (C++)'
title: Proje kaynak dosyaları (C++)
ms.date: 05/14/2019
helpviewer_keywords:
- resource files
- resources [C++]
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
ms.openlocfilehash: 2e0dbafdab2b13dd4757008e56b92fb5622e25b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225160"
---
# <a name="project-resource-files-c"></a>Proje kaynak dosyaları (C++)

Kaynaklar, kullanıcıya bilgi sağlayan arabirim öğeleridir. Bit eşlemler, simgeler, araç çubukları ve imleçler tüm kaynaklardır. Bazı kaynaklar bir menüden seçme veya iletişim kutusunda veri girme gibi bir eylem gerçekleştirebilir.

Daha fazla bilgi için bkz. [kaynaklarla çalışma](../../windows/working-with-resource-files.md).

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*ProjName*. RC|*ProjName*|Kaynak dosyalar|Projenin kaynak betik dosyası. Kaynak betik dosyası, proje türüne ve proje için seçilen desteğe (örneğin, araç çubukları, iletişim kutuları veya HTML) bağlı olarak aşağıdakileri içerir:<br /><br />-Varsayılan menü tanımı.<br />-Hızlandırıcı ve dize tabloları.<br />-Varsayılan **hakkında** iletişim kutusu.<br />-Diğer iletişim kutuları.<br />-Icon dosyası (Res \\ *ProjName*. ico).<br />-Sürüm bilgileri.<br />Biteşlem.<br />Toolbar.<br />-HTML dosyaları.<br /><br /> Kaynak dosyası, standart Microsoft Foundation Class kaynakları için afxres. rc dosyasını içerir.|
|Kaynak.h|*ProjName*|Üstbilgi Dosyaları|Proje tarafından kullanılan kaynaklar için tanımları içeren kaynak üstbilgi dosyası.|
|*ProjName*. RC2|*ProjName*\res|Kaynak dosyalar|Proje tarafından kullanılan ek kaynakları içeren betik dosyası. . RC2 dosyasını projenin. rc dosyasına ekleyebilirsiniz.<br /><br /> Bir. rc2 dosyası, birkaç farklı proje tarafından kullanılan kaynakları dahil etmek için kullanışlıdır. Farklı projeler için aynı kaynakları birkaç kez oluşturmak yerine bunları bir. RC2 dosyasına yerleştirebilir ve. RC2 dosyasını Main. rc dosyasına ekleyebilirsiniz.|
|*ProjName*. def|*ProjName*|Kaynak dosyalar|DLL projesi için modül tanım dosyası. Bir denetim için, denetimin adını ve açıklamasını, ayrıca çalışma zamanı yığınının boyutunu sağlar.|
|*ProjName*. ico|*ProjName*\res|Kaynak Dosyalar|Proje veya denetim için simge dosyası. Bu simge, uygulama simge durumuna küçültüldüğünde görüntülenir. Ayrıca, uygulamanın **hakkında** kutusunda da kullanılır. MFC, varsayılan olarak MFC simgesini sağlar ve ATL ATL simgesini sağlar.|
|*ProjName* Doc. ico|*ProjName*\res|Kaynak Dosyalar|Belge/görünüm mimarisi için destek içeren bir MFC projesinin simge dosyası.|
|Toolbar.bmp|*ProjName*\res|Kaynak Dosyalar|Bir araç çubuğundaki veya paletteki uygulamayı veya denetimi temsil eden bit eşlem dosyası. Bu bit eşlem projenin kaynak dosyasına dahildir. İlk araç çubuğu ve durum çubuğu, **Canabilgisayar** sınıfında oluşturulur.|
|Ribbon. mfcribbon-ms|*ProjName*\res|Kaynak Dosyalar|Şeritteki düğmeleri, denetimleri ve öznitelikleri tanımlayan XML kodunu içeren kaynak dosyası. Daha fazla bilgi için bkz. [Şerit Tasarımcısı (MFC)](../../mfc/ribbon-designer-mfc.md).|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)
