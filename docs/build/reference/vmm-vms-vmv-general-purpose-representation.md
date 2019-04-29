---
title: / VMM, - vms, - vmv (genel amaçlı temsil)
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 7a46cecdbf96ad891ce218df4769a60590e562a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316736"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv (Genel Amaçlı Temsil)

Kullanılabilir [/vmb, / vmg (temsil yöntemi)](vmb-vmg-representation-method.md) olarak seçilen [temsil yöntemi](vmb-vmg-representation-method.md). Bu seçenekler, henüz karşılaştı sınıf tanımının devralma modeli belirtin.

## <a name="syntax"></a>Sözdizimi

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>Açıklamalar

Seçenekler aşağıdaki tabloda açıklanmıştır.

|Seçenek|Açıklama|
|------------|-----------------|
|**/vmm**|Birden fazla devralma kullanan bir olacak şekilde bir sınıf üyesinin işaretçisinin en genel gösterim belirtir.<br /><br /> Buna karşılık gelen [devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişken [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) olduğu **birden çok devralma**.<br /><br /> Bu gösterim tek devralma için gereken değerinden daha büyük.<br /><br /> Bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise, derleyici bir hata oluşturur.|
|**/ VMs**|Hiçbir devralma veya tek devralma kullanan bir olacak şekilde bir sınıf üyesinin işaretçisinin en genel gösterim belirtir.<br /><br /> Buna karşılık gelen [devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişken [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) olduğu **single_inheritance**.<br /><br /> Bu bir sınıfın bir üye işaretçisi en küçük olası gösterimidir.<br /><br /> Bir üye işaretçisi olarak bildirilen bir sınıf tanımının devralma modeli birden fazla ise veya sanal, derleyici bir hata oluşturur.|
|**/vmv**|Sanal devralma kullanan bir olacak şekilde bir sınıf üyesinin işaretçisinin en genel gösterim belirtir. Bu, hiçbir zaman hataya neden olur ve varsayılandır.<br /><br /> Buna karşılık gelen [devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişken [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) olduğu **virtual_inheritance**.<br /><br /> Bu seçenek, bir işaretçiyi daha büyük ve diğer seçeneklerden işaretçiyi yorumlamak için ek kod gerektirir.|

Bu devralma modeli seçeneklerden birini belirttiğinizde, bu modelin tüm işaretçileri, devralma türü veya işaretçiyi önce veya bildirildiği sınıf sonra bağımsız olarak, sınıf üyeleri için kullanılır. Her zaman tek devralımlı sınıflara kullanırsanız, bu nedenle, istediğiniz kod boyutu ile derleme tarafından azaltabilirsiniz **/VMs**; ancak, en genel durum (çoğaltamaz en büyük veri temsilini) kullanmak istiyorsanız, ilederleme **/vmv**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/vmb, /vmg (Temsil Yöntemi)](vmb-vmg-representation-method.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
