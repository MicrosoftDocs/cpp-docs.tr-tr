---
title: ARM Assembler komut satırı başvurusu
description: Microsoft ARM Assembler komut satırı seçeneklerine yönelik başvuru kılavuzu.
ms.date: 02/09/2020
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
ms.openlocfilehash: a63273e8d21e7a28574ec79d62c15f29ee59cd50
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257385"
---
# <a name="arm-assembler-command-line-reference"></a>ARM Assembler komut satırı başvurusu

Bu makalede, Microsoft ARM Assembler, **armasd**ile ilgili komut satırı bilgileri sağlanmaktadır. **armase** , ARMv7 Thumb derleme dilini ortak nesne dosyası BIÇIMI (COFF) Microsoft uygulamasına ayrıştırır. Bağlayıcı, hem ARM Assembler hem de C derleyicisi tarafından oluşturulan COFF kod nesnelerini bağlayabilir. Kütüphaneian tarafından oluşturulan nesne kitaplıklarıyla birlikte bağlantı oluşturabilir.

## <a name="syntax"></a>Sözdizimi

> **`armasm`** [*seçenekler*] *source_file* *object_file*\
> **`armasm`** [*seçenekler*] **`-o`** *object_file* *source_file*

### <a name="parameters"></a>Parametreler

*seçenekler*\
Sıfır veya daha fazla seçenekten oluşan bir bileşim:

- **`-errors`** *dosya adı*\
   Hata ve uyarı iletilerini *dosya adına*yönlendirin.

- **`-i`** *dir*[ **`;`** <em>dir</em>] \
   Belirtilen dizinleri ekleme arama yoluna ekleyin.

- **`-predefine`** *yönergesi*\
   Bir sembolü pretanýmlamak için SETA, SETL veya SETS yönergesini belirtin. \
   Örnek: `armasm.exe -predefine "COUNT SETA 150" source.asm`\
   Daha fazla bilgi için [ARM derleyicisi arması başvuru kılavuzu](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)' na bakın.

- **`-nowarn`**\
   Tüm uyarı iletilerini devre dışı bırakın.

- **`-ignore`** *Uyarı*\
   Belirtilen uyarıyı devre dışı bırakın. Olası değerler için, uyarılar hakkında bölümüne bakın.

- **`-help`**\
   Komut satırı yardım iletisini yazdır.

- **`-machine`** *makine*\
   PE üstbilgisinde ayarlanacak makine türünü belirtin.  *Makinenin* olası değerleri şunlardır: \
   **ARM**— makine türünü IMAGE_FILE_MACHINE_ARMNT olarak ayarlar. Bu seçenek varsayılandır. \
   **Thumb**— makine türünü IMAGE_FILE_MACHINE_THUMB olarak ayarlar.

- **`-oldit`**\
   ARMv7-Style It blokları oluşturun.  Varsayılan olarak, ARMv8 uyumlu BT blokları oluşturulur.

- **`-via`** *dosya adı*\
   *Dosya adından*ek komut satırı bağımsız değişkenlerini okuyun.

- **`-16`**\
   Kaynağı 16 bit Thumb yönergeleri olarak birleştirin.  Bu seçenek varsayılandır.

- **`-32`**\
   Kaynağı 32-bit ARM yönergeleri olarak birleştirin.

- **`-g`**\
   Hata ayıklama bilgileri oluştur.

- **`-errorReport:`** *seçenek*\
   Bu seçenek kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

*source_file*\
Kaynak dosyasının adı.

*object_file*\
Nesne (çıktı) dosyasının adı.

## <a name="remarks"></a>Açıklamalar

Aşağıdaki örnekte, armasd 'nin tipik bir senaryoda nasıl kullanılacağı gösterilmektedir. İlk olarak, bir nesne (. obj) dosyasına bir derleme dili kaynağı (. asm) dosyası oluşturmak için armasd kullanın. Ardından, bir kaynak (. C) dosyası derlemek ve ayrıca ARM nesne dosyasını bağlamak için bağlayıcı seçeneğini belirtmek üzere CL komut satırı C derleyicisini kullanın.

```cmd
armasm myasmcode.asm -o myasmcode.obj
cl myccode.c /link myasmcode.obj
```

## <a name="see-also"></a>Ayrıca bkz.

[ARM Assembler tanılama iletileri](../../assembler/arm/arm-assembler-diagnostic-messages.md)\
[ARM Assembler yönergeleri](../../assembler/arm/arm-assembler-directives.md)
