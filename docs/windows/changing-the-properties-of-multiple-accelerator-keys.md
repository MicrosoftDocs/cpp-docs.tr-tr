---
title: (C++) birden çok hızlandırma tuşunun özelliklerini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 56deca345915c5736cb15e7ce5d8d0e0ee0b7062
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400801"
---
# <a name="changing-the-properties-of-multiple-accelerator-keys-c"></a>(C++) birden çok hızlandırma tuşunun özelliklerini değiştirme

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Birden çok hızlandırma tuşunun özelliklerini değiştirme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Hızlandırıcı tuşları basılı tutarak değiştirmek istediğiniz seçin **Ctrl** anahtar her birini tıklatın.

3. Git [Özellikler penceresi](/visualstudio/ide/reference/properties-window) tüm paylaşmak için seçilen Hızlandırıcılar istediğiniz değerleri yazın.

   > [!NOTE]
   > Her değiştiricisi değer bir Boolean özelliği olarak görünür **özellikleri** penceresi. Değiştirirseniz bir [değiştiricisi](../windows/accelerator-modifier-property.md) değerini **özellikleri** penceresinde Hızlandırıcı tablosunu işler yeni değiştiricisini ek olarak, önceden var olan tüm değiştiriciler. Herhangi bir değiştirici değeri ayarlarsanız, bu nedenle, her hızlandırıcının aynı paylaşımları sağlamak için bunların tümünü ayarlamak ihtiyacınız olacak **değiştiricisi** ayarları.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tablolarını Düzenleme](../windows/editing-accelerator-tables.md)<br/>
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)