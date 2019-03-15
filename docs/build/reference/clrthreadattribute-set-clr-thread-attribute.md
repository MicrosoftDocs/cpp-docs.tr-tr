---
title: /CLRTHREADATTRIBUTE (CLR İş Parçacığı Özniteliğini Ayarla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: ad07c84a5c470cd5fa1ac10ff6d2baed5c35c025
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57806785"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (CLR İş Parçacığı Özniteliğini Ayarla)

CLR programınızın giriş noktası için iş parçacığı oluşturma özniteliğini açıkça belirtin.

## <a name="syntax"></a>Sözdizimi

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>Parametreler

**MTA**<br/>
Programınızın Giriş noktasına MTAThreadAttribute özniteliğini uygular.

**YOK**<br/>
/CLRTHREADATTRIBUTE belirtmeme işlemiyle aynıdır.  İş parçacığı oluşturma özniteliği varsayılan ortak dil çalışma zamanı (CLR) olanak sağlar.

**STA**<br/>
Programınızın Giriş noktasına STAThreadAttribute özniteliğini uygular.

## <a name="remarks"></a>Açıklamalar

Ana iş parçacığı giriş noktası etkileyen iş parçacığı özniteliği yalnızca .exe, oluşturma sırasında geçerli ayardır.

Kullanırsanız yerleştirerek iş parçacığı oluşturma özniteliği (STAThreadAttribute veya MTAThreadAttribute) varsayılan giriş işlev veya varsayılan giriş noktası (main veya wmain, örneğin) /CLRTHREADATTRIBUTE kullanılarak iş parçacığı modeli belirtin.

Varsayılan olmayan giriş noktası kullanıyorsanız, iş parçacığı modeli /CLRTHREADATTRIBUTE kullanarak veya iş parçacığı yerleştirerek öznitelik varsayılan olmayan giriş işlev ve ardından varsayılan olmayan giriş noktasıyla belirtin belirtin [/Entry](entry-entry-point-symbol.md) .

Kaynak kodunda belirtilen iş parçacığı modeli ile /CLRTHREADATTRIBUTE belirtilen iş parçacığı modeliyle kabul etmezse, bağlayıcı /CLRTHREADATTRIBUTE yoksay ve kaynak kodunda belirtilen iş parçacığı modeli geçerlidir.

CLR programınızın tek iş parçacığı kullanan bir COM nesnesi barındırıyorsa, örneğin, tek iş parçacığı, kullanmanız için gerekli olacaktır.  CLR çoklu iş parçacığı kullanan programda, tek iş parçacığı kullanan bir COM nesnesi barındıramaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **CLR iş parçacığı özniteliği** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
