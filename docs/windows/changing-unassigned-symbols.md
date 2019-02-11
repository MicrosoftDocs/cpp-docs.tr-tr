---
title: Atanmamış sembolleri silme veya değiştirme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.unassigned
helpviewer_keywords:
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
ms.assetid: b6abee4a-3c24-4697-a166-fe6a86cad35f
ms.openlocfilehash: 47cc3d7a387092afe77fdbcf4bbdb6d085eeda25
ms.sourcegitcommit: 966e4466f10c93fc12faf33d28e03b39489423fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2019
ms.locfileid: "55987020"
---
# <a name="changing-or-deleting-unassigned-symbols"></a>Atanmamış sembolleri silme veya değiştirme

İçinde çalışırken [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md), düzenlemek veya bir kaynak veya nesne zaten atanmamış varolan sembolleri Sil.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="to-change-an-unassigned-symbol"></a>Atanmamış bir sembol değiştirmek için

1. İçinde **adı** kutusuna atanmamış simgesini seçin ve seçin **değişiklik**.

1. Simgenin adı veya değeri, verilen kutulara Düzenle **sembolü Değiştir** iletişim kutusu.

   > [!NOTE]
   > Bir sembol değiştirmek için *olduğu* bir kaynağa veya nesne atanan kaynak düzenleyicisini kullanmanız gerekir veya **özellikleri** penceresi. Daha fazla bilgi için [sembolü veya sembol adını değiştirme](../windows/changing-a-symbol-or-symbol-name-id.md).

## <a name="to-delete-an-unassigned-unused-symbol"></a>Atanmamış bir (kullanılmayan) sembolü silmek için

İçinde [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md), silme ve istediğiniz simgeyi seçin **Sil**.

   > [!NOTE]
   > Kullanılmayan bir sembol kaynak dosya silinmeden önce başka bir program veya kaynak dosyaları derleme zamanında dahil tarafından kullanılmadığından emin olun.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Sembollerini Görüntüleme](../windows/viewing-resource-symbols.md)<br/>
[Sembol Adı Kısıtlamaları](../windows/symbol-name-restrictions.md)<br/>
[Sembol Değeri Kısıtlamaları](../windows/symbol-value-restrictions.md)<br/>
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)