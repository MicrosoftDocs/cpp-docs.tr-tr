---
title: Simgeler için görüntü Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, images
- resource editors, graphics
- Image editor [C++]
- resource editors, Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4f038dea14aedc4016746297ac99aedd57445eb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215847"
---
# <a name="image-editor-for-icons"></a>Simgeler İçin Görüntü Düzenleyicisi

Resim düzenleyicisi, resim oluşturmak ve düzenlemek için kapsamlı bir araç kümesi ve ayrıca, araç çubuğu bit eşlemleri oluşturmanıza yardımcı olacak özellikler içerir. Bit eşlemler, simgeler ve imleçlerin yanı sıra komutlarını kullanarak GIF veya JPEG biçimindeki görüntüleri de düzenleyebilirsiniz **görüntü** menü ve araçları **Resim Düzenleyicisi** araç çubuğu.

Resim düzenleyicisi ile yapabilecekleriniz:

- [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)

- [Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)

- [Simgeler ve İmleçler ile çalışma: ekran cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [Resim Düzenleyicisi komutları için kısayol tuşlarını kullanın](../windows/accelerator-keys-image-editor-for-icons.md)

**Resim Düzenleyicisi** görüntünün iki bölme çubukla bölme ile iki Görünüm penceresi gösterir. Bölmelerin göreli boyutlarını değiştirmek için bölme çubuğunu yanlara doğru sürükleyebilirsiniz. Etkin bölmede bir seçim kenarlığı görüntülenir.

**Resim Düzenleyicisi** penceresi, gereksinimlerinize ve tercihlerinize uyacak şekilde ayarlanabilir. Yapabilecekleriniz [büyütme katsayısını değiştirme](../windows/changing-the-magnification-factor-image-editor-for-icons.md) ve [görüntülemek veya piksel ızgarasını](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

## <a name="visual-studio-image-library"></a>Visual Studio Görüntü Kitaplığı

Ücretsiz olarak indirebilirsiniz **Visual Studio görüntü kitaplığı** birçok animasyon, bit eşlemler ve uygulamalarınızda kullanabileceğiniz simgeler içeriyor. Kitaplığı indirme hakkında daha fazla bilgi için bkz. [Visual Studio Resim Kitaplığı](/visualstudio/designers/the-visual-studio-image-library).

## <a name="managed-resources"></a>Yönetilen Kaynaklar

Kullanabileceğiniz **görüntü** Düzenleyicisi ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Simgeler](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)