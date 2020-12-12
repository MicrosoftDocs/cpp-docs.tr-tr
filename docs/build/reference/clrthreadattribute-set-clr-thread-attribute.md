---
description: Daha fazla bilgi edinin:/CLRTHREADATTRıBUTE (CLR Iş parçacığı özniteliğini ayarla)
title: /CLRTHREADATTRIBUTE (CLR İş Parçacığı Özniteliğini Ayarla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: 119797ee10ed0c08477b8e08635605e4299ffd41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179128"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (CLR İş Parçacığı Özniteliğini Ayarla)

CLR programınızın giriş noktası için iş parçacığı oluşturma özniteliğini açıkça belirtin.

## <a name="syntax"></a>Sözdizimi

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>Parametreler

**MTA**<br/>
Programınızın giriş noktasına MTAThreadAttribute özniteliğini uygular.

**SEÇIM**<br/>
/CLRTHREADATTRIBUTEAS Belirtmemeye benzer.  Ortak dil çalışma zamanının (CLR) varsayılan iş parçacığı özniteliğini ayarlamaya izin verir.

**A**<br/>
Programınızın giriş noktasına STAThreadAttribute özniteliğini uygular.

## <a name="remarks"></a>Açıklamalar

Thread özniteliğinin ayarlanması, ana iş parçacığının giriş noktasını etkilediği için yalnızca bir. exe oluşturulurken geçerlidir.

Varsayılan giriş noktasını (örneğin, Main veya wmain) kullanıyorsanız iş parçacığı modelini/CLRTHREADATTRıBUTE kullanarak veya varsayılan giriş işlevine iş parçacığı özniteliği (STAThreadAttribute veya MTAThreadAttribute) koyarak belirtin.

Varsayılan olmayan bir giriş noktası kullanırsanız,/CLRTHREADATTRıBUTE kullanarak veya iş parçacığı oluşturma özniteliğini varsayılan olmayan giriş işlevine yerleştirerek ya da varsayılan olmayan giriş noktasını [/Entry](entry-entry-point-symbol.md)ile belirterek iş parçacığı modelini belirtin.

Kaynak kodda belirtilen iş parçacığı modeli,/CLRTHREADATTRıBUTE ile belirtilen iş parçacığı modeliyle uyuşmadığından, bağlayıcı/CLRTHREADATTRıBUTE 'yi yoksayar ve kaynak kodunda belirtilen iş parçacığı modelini uygular.

Örneğin, CLR programınız tek iş parçacığı kullanan bir COM nesnesi barındıralıyorsa, tek iş parçacığı kullanmanız gerekir.  CLR programınız çoklu iş parçacıklı kullanıyorsa, tek iş parçacığı kullanan bir COM nesnesini barındıraamaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Gelişmiş** özellik sayfasını seçin.

1. **Clr Iş parçacığı özniteliği** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
