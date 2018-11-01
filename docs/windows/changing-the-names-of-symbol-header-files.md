---
title: Sembol Başlık Dosyalarının Adlarını Değiştirme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.header
helpviewer_keywords:
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
ms.openlocfilehash: 4d9aa350d0f680e975c68bf46ac066072df044cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432346"
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

[Kaynak Sembollerini Görüntüleme](../windows/viewing-resource-symbols.md)<br/>
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)