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
ms.openlocfilehash: 51470a572ec9540f203bb4cff80981fe6ad15dd1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578577"
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

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme için kaynakların kullanarak](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Dizeler](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)  
[Dizeleri hakkında](/windows/desktop/menurc/about-strings)

