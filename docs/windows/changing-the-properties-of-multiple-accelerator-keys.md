---
title: Birden çok hızlandırma tuşunun özelliklerini değiştirme | Microsoft Docs
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
ms.openlocfilehash: 11705fcbcdb3dc73fe5c3a87844b2bc5d90cd135
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="changing-the-properties-of-multiple-accelerator-keys"></a>Birden Çok Hızlandırma Tuşunun Özelliklerini Değiştirme
### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Birden çok hızlandırma tuşunun özelliklerini değiştirmek için  
  
1.  Hızlandırıcı tablosunu simgesini çift tıklatarak açın [kaynak görünümü](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Basılı tutarak değiştirmek istediğiniz Hızlandırıcı tuşları seçin **CTRL** anahtar her birini tıklatın.  
  
3.  Git [Özellikler penceresini](/visualstudio/ide/reference/properties-window) paylaşmak için seçilen Hızlandırıcıları tümünün istediğiniz değerleri yazın.  
  
    > [!NOTE]
    >  Her değiştirici değeri Özellikleri penceresinde bir Boolean özelliği olarak görünür. Değiştirirseniz bir [değiştiricisi](../windows/accelerator-modifier-property.md) Hızlandırıcı tablosu özellikleri penceresinde değer ek olarak daha önce vardı değiştiricileri new değiştiricisi değerlendirir. Herhangi bir değiştirici değeri ayarlarsanız bu nedenle, her Hızlandırıcı aynı değiştiricisi ayarları paylaşımları sağlamak için bunların tümünün ayarlamanız gerekir.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tablolarını düzenleme](../windows/editing-accelerator-tables.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)