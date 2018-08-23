---
title: Sembol başlık dosyalarının adlarını değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.header
dev_langs:
- C++
helpviewer_keywords:
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2df697df91374b61b72b9093c8cf16e1ac613863
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605232"
---
# <a name="changing-the-names-of-symbol-header-files"></a>Sembol Başlık Dosyalarının Adlarını Değiştirme

Normalde tüm sembol tanımlarını kaydedilir `Resource.h`. Ancak, bunu değiştirmeniz gerekebilir, örneğin, birden fazla kaynak dosyayla aynı dizinde çalışabilir böylece dosya adı içermelidir.

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>Kaynak sembol başlık dosyası adını değiştirmek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasını sağ tıklatın ve seçin [kaynak içerikleri](../windows/resource-includes-dialog-box.md) kısayol menüsünden.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde **sembol başlık dosyası** içerme dosyası için yeni bir ad yazın.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Sembollerini Görüntüleme](../windows/viewing-resource-symbols.md)  
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)