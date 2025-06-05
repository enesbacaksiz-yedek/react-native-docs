# react-native-docs
#React native notları

1) projeyi oluşturmak için dökümantasyonda yer alan "npx create-expo-app@latest" kodunu terminalde çalıştırırız.
2) Daha sonra terminalde cd + projemizi oluştururken verdiğimiz proje adını yazarak klasöre giriş yapıyoruz
3) Ardından projeyi sıfırdan resetlememiz daha uygun olacağı için "npm run reset-project" komutu ile projemizi daha temiz hale getiriyoruz

Uygulama açma adımları için https://reactnative.dev/docs/ linkinden yararlanabilirsiniz.

Aşağıda var olan bilgiler madde madde yapılması gerekenler şeklinde olacaktır.

- Projeyi başlatmak için yeni bir klasör içinde vscode’ ı açıp `npx create-expo-app@latest`  komutunu çalıştırırız.
- Uygulama expo ile çalışacağı için uygulamayı başlatmak için proje dosyamızın içine `cd + klasör adı`  yazarak içine girip `expo start`  komutunu çalıştırmamız gerekir.
- Ardından eğer bir android cihazda çalışacak isek oluşan QR ‘ı okutmamız, emulatör ile çalışacak isek de (windows) a tuşuna basıp emulatorde ilk first-app i çalıştırabiliriz.

AŞAĞIDA DOSYA YAPILARININ İÇLERİNDE NELER OLDUĞUNU ANLATIYOR OLACAĞIZ

| 

app/ | - Uygulamanın navigasyon yapısını barındırır
- `app/(tabs)/index.tsx` → Tab navigator’un ana sayfası
- `appp/(tabs)/explore.tsx` → başka bir sekme sayfası
- `app/(tabs)/_layout.tsx` → sekmelerin (tabs) görünüm ve davranışlarını kontrol eden layout dosyası
- Bu klasör, uygulamanın temel UI akışını ve yönlendirmeyi organize eder. |
| --- | --- |
| 
assets/ | - Görsel, ikon, font, ses gibi statik medya varlıklarını barındırır
* logo.png, background.jpg, custom-font.ttf |
| 

components/ | - Uygulmanın içinde tekrar tekrar kullanılan, bileşenlerin (componentlerin) saklandığı klasördür
- Butonlar, kartlar, özel UI parçaları gibi bağımsız ve modüler React bileşenleri burada yer alır |
| 

 constants/ | - Uygulamada kullanılan sabi değerlerin (renk paletleri, ölçü birimleri, API endpointleri, metin sabitleri) tutulduğu klasör
* Renk teması `colors.ts` , uygulama genelinde kullanılan sabit metinler, boyutlar vb. |
| 

hooks/ |  - React’in özel veya ortak kullanılan custom hook’larının tutulduğu klasör
- Örneğin, veri çekme için `useFetch.ts` , tema yönetimi için `useTheme.ts`  gibi fonksiyonlar burada saklanır
- Kodun tekrarını azaltır ve fonksiyonel mantığı ayrıştırır. |
| 

scripts/ | - Proje ile ilgili özel yardımcı scriptlerin konduğu klasör
* Otomatik kd formatlama, build veya deploy işlemleri için kullanılan betikler olabilir.
- Genellikle proje yönetimini kolaylaştıran araçlar burada olur |
| 

app.json |  - Expo projesinin yapılandırma (config) dosyasıdır. 
- Uygulama adı, ikon, sürüm, splash screen, platformlara özel ayarlar burada belirlenir.
- Expo’nun build ve publish işlemleri bu dosyaya dayanır. |
| 

pacjage.json | - Projenin bağımlılıkları ve scriptlerini tanımlar
- Hangi kütüphanelerin yüklü olduğu, start, build, test komutları buradadır. |
| tsconfig.json | - TypeScript derleyici ayarlarının olduğu dosyadır.
- Projede TypeScript kullanılıyorsa, buradaki kurallar doğrultusunda kod derlenir.
* Örneğin hedef JS sürümü, modül çözümleme, dosya dışıreferanslar gibi ayarlar burada yapılır |

Özet Tablosu

| Klasör/Dosya | Görevi |
| --- | --- |
| **app/** | Navigasyon ve sayfa yapısı (file-based routing) |
| **assets/** | Görsel, font, ses vb. medya dosyaları |
| **components/** | Tekrar kullanılabilir React bileşenleri |
| **constants/** | Sabit değerler (renkler, metinler, API adresleri vb.) |
| **hooks/** | Custom React hook’ları |
| **scripts/** | Yardımcı geliştirme/built scriptleri |
| **app.json** | Expo proje yapılandırma dosyası |
| **package.json** | Proje bağımlılıkları ve npm scriptleri |
| **tsconfig.json** | TypeScript derleyici ayarları |

Örnek Tablosu 2

| Klasör / Dosya | Görev / Açıklama | Somut Örnek (Ne Var, Nasıl Kullanılır?) |
| --- | --- | --- |
| **app/** | Uygulamanın sayfaları ve navigasyon yapısı. | 3 sayfa var: `index.tsx` (Ana Sayfa), `explore.tsx` (Keşfet), `_layout.tsx` (Sekme menü düzeni) |
| **assets/** | Görseller, ikonlar, fontlar gibi medya dosyaları. | `logo.png` (app logosu), `background.jpg` (arka plan resmi) |
| **components/** | Tekrar kullanılabilir UI parçaları (buton, kart, liste vb.) | `Button.tsx` (özelleştirilmiş buton), `Card.tsx` (ürün kartı) |
| **constants/** | Uygulama genelinde kullanılan sabit değerler. | `colors.ts` dosyasında: primary="#4A90E2", secondary="#F5A623" |
| **hooks/** | Özel işlevsel React hook’ları (fonksiyonlar) | `useFetch.ts` (API’den veri çekme fonksiyonu) |
| **scripts/** | Proje otomasyon ve yardımcı komut dosyaları | `clean.js` — dosya temizleme scripti, `build.js` — otomatik derleme |
| **app.json** | Expo proje ayarları (isim, versiyon, ikon) | Uygulama adı: "MyApp", versiyon: "1.0.0", ikon: `assets/icon.png` |
| **package.json** | Proje bağımlılıkları ve npm/yarn scriptleri | `dependencies` içinde "react-native", "expo"; `scripts` içinde "start": "expo start" |
| **tsconfig.json** | TypeScript derleyici ayarları | Target ESNext, JSX modu React JSX olarak ayarlanmış |

- Proje sıfırlamak için `npm run reset-project`  komutu kullanabiliriz.

## STYLE

- Çoğu uygulama aşağıdaki basic componentslerden bir veya daha fazlasını projelerinde kullanır

### **Basic Components**

- View
- Text
- Image
- TextInput
- ScrololView
- StyleSheet

### **View**

- Kullanıcı Arayüzü oluşturmak için en temel bileşendir `<view></view>`
- Bir kapsayıcıdır
- Aynı web porjelerinde bulunan `<div></div>`  etiketi gibi

### **Sanallaştırılmış Liste - VirtualizedList**

- Buna şöyle diyebiliriz mesela elimizde bir liste var bunlar bir uygulamanın ürün listeleri olsun. Bir anda verileri yükleyip göstermek yerine (bu uygulamamızın çökmesine, kasmasına vb durummlara sebep olur) sadece o sayfada ne kadar sığdırıyorsa o kadar gösterir ve ona göre yenileyerek devam eder
- Örneğin 1-10 , 11, 20 şeklinde sayfada aşağıya kaydıkça gösterir.
- `FlatList`, `SectionList` gibi bileşenlerin altyapısını oluşturan bileşendir. Çok fazla öğe varsa hepsini aynı anda render etmek yerine **sadece görünürde olanları** render ederek performansı artırır.
- Ne zaman kullanılır
    - 10.000+ veri varsa
    - Kendi özel listeni yazmak istiyorsan ama performans da önemliyse
- Temel Özellikleri
    - `data`: Gösterilecek veri dizisi **yok** → onun yerine `getItemCount` ve `getItem` kullanılır.
    - `renderItem`: Her öğeyi nasıl çizeceğini tanımlar.
    - `initialNumToRender`: İlk kaç öğe yüklensin.
    - `maxToRenderPerBatch`: Aynı anda kaç öğe render edilsin.
    - `windowSize`: Görünürdeki ekranın kaç katı kadar öğe bellekte tutulsun.

```tsx
import { VirtualizedList, Text } from 'react-native';

const data = Array.from({ length: 1000 }, (_, i) => `Öğe #${i + 1}`);

const getItem = (_, index) => data[index];
const getItemCount = () => data.length;

export default function App() {
  return (
    <VirtualizedList
      data={data}
      initialNumToRender={10}
      renderItem={({ item }) => <Text>{item}</Text>}
      keyExtractor={(item, index) => index.toString()}
      getItemCount={getItemCount}
      getItem={getItem}
    />
  );
}

```

- `VirtualizedList` ve `Text` bileşenlerini React Native'den içe aktarıyoruz.
- `VirtualizedList` listeyi performanslı gösteren yapı.
- `Text`, ekranda yazı göstermek için.
- Bu satırda sahte bir veri listesi oluşturuluyor.
- 1000 tane `Öğe #1`, `Öğe #2`, ... gibi string’ler içeren bir dizi.
- `Array.from` → yeni dizi oluşturur.
- `(_, i)` → sadece index (`i`) önemli.
- `VirtualizedList`, `data` dizisini **otomatik** kullanmaz.

       Bu yüzden:

- `getItem`: Belirli bir index'teki veriyi döner.
- `getItemCount`: Toplam kaç öğe var, onu döner.

| Prop | Açıklama |
| --- | --- |
| `data={data}` | Sahte veri dizimiz. Ama doğrudan kullanmaz, `getItem`, `getItemCount` gerekir. |
| `initialNumToRender={10}` | Uygulama açıldığında ilk kaç öğe yüklensin? Burada 10 tane. |
| `renderItem={({ item }) => <Text>{item}</Text>}` | Her bir veri öğesini `Text` ile gösterir. |
| `keyExtractor={(item, index) => index.toString()}` | Her öğeye benzersiz anahtar verir. (Zorunlu) |
| `getItemCount` ve `getItem` | Veriye erişmek için gerekli fonksiyonlar |
