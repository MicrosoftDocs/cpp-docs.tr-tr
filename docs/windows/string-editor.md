---
title: Dize Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string.F1
dev_langs:
- C++
helpviewer_keywords:
- String editor
- string tables
- string tables, String editor
- string editing
- string editing, string tables
- resource editors, String editor
- strings [C++], editing
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 903c477117162dde1d0becc6e2196e683ea189f1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196816"
---
# <a name="string-editor"></a>Dize Düzenleyicisi

Dize tablosu kimlikleri, değerleri ve açıklamalı alt yazılar, uygulamanızın tüm dizeleri listesini içeren bir Windows kaynaktır. Örneğin, durum çubuğu komut istemlerini dize tablosunda yer alır.

Bir uygulama geliştirirken birden çok dize tabloları olabilir — her dilini veya koşulunu biri. Ancak, yalnızca bir dize tablosu bir çalıştırılabilir modüle sahiptir. Tabloları farklı dll koyarsanız çalışan bir uygulama birden çok dize tabloları başvurabilirsiniz.

Dize tabloları uygulamanızın farklı dillere yerelleştirilmesi kolaylaştırır. Tüm dizeler dize tablosunda, dizeleri (ve diğer kaynakları) kaynak kodunda değişiklik yapmadan çevirerek uygulama yerelleştirebilirsiniz. Bu el ile dizeleri bulma ve çeşitli kaynak dosyalarında değiştirme daha genellikle daha tercih edilir.

Dize Düzenleyicisi'ni kullanarak şunları yapabilirsiniz:

- [Bir veya daha fazla dizeleri arama](../windows/finding-a-string.md).

- Hızlı bir şekilde [yeni girişler ekleyin](../windows/adding-or-deleting-a-string.md) dize tablosu.

- [Bir dizeyi bir kaynak dosyasından diğerine taşıma](../windows/moving-a-string-from-one-resource-file-to-another.md)

- [Yerinde düzenleme kimliği, değer ve açıklamalı alt yazı özelliklerini kullanmak](../windows/changing-the-properties-of-a-string.md) ve hemen değişiklikleri görüntüleyin.

- [Birden çok dizenin resim yazısı özelliğini değiştirme](../windows/changing-the-caption-property-of-multiple-strings.md)

- [Dizeye biçimlendirme veya özel karakterler ekleme](../windows/adding-formatting-or-special-characters-to-a-string.md)

   > [!NOTE]
   > Windows, boş dize tabloları oluşturulmasına izin vermiyor. Dize tablosu giriş yok oluşturursanız, kaynak dosyasını kaydettiğinizde, otomatik olarak silinir.

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Dizeler](https://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)  
[Dizeleri hakkında](/windows/desktop/menurc/about-strings)

