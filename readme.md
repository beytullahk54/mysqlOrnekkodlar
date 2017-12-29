
CREATE DATABASE kartsis;

CREATE TABLE `il` (  `id` int(11)  PRIMARY KEY AUTO_INCREMENT,  `il_adi` varchar(15) ) ;

CREATE TABLE `il_tarife` (  `id` int(11)  PRIMARY KEY AUTO_INCREMENT,  `il_id` int(11) ,  `il_vasita_tur` varchar(15) ,  `il_vasita_ad` varchar(15) ,  `il_vasita_fiyat` varchar(15) ) ;

CREATE TABLE `uyeler` (  `id` int(11)  PRIMARY KEY AUTO_INCREMENT,  `kart_no` int(11) , `tur` varchar(15), `adi` varchar(15) ,  `soyadi` varchar(15) ,  `sifre` varchar(15) ,  `il_id` varchar(2) ,  `bakiye` float(11) ) ;

INSERT INTO `il_tarife` (`id`, `il_id`, `il_vasita_tur`, `il_vasita_ad`, `il_vasita_fiyat`) VALUES(1, 1, 'Ogrenci', 'Otobüs', '1.50');

INSERT INTO `il` (`id`, `il_adi`) VALUES(1, 'Adana');

INSERT INTO `uyeler` (`id`, `kart_no`, `adi`, `soyadi`, `sifre`, `il_id`, `bakiye`,`tur`) VALUES(1, 101010, 'burak', 'öner', '123456', '1', 10,`Ogrenci`);


/* Kart basıldığında bakiye düşüren mysql */

SELECT `bakiye`,`tur`,`il_id` FROM `uyeler` WHERE `id` = 1 /*1)Fiyatı ve türü Al (1 yerine kartı basan kişinin idsi) */
SELECT `il_vasita_fiyat` FROM `il_tarife` WHERE `il_vasita_tur`='Ogrenci' AND `il_id` = '1'  /*2)Kartın Basıldığı aracın basan kişinin yaşadığı id */
/*3) bakiyeden il vasıta fiyatı düş ve yeni değişkene ata  10-1.5=8.5 */
UPDATE `uyeler` SET`bakiye`= 8.5 WHERE `id` = 1 /*4)Yeni fiyatı uyeler tablosundan güncelle*/

/* Kart basıldığında bakiye düşüren sql */

/*Karta Para Yükleme mysql Kodları*/

SELECT `bakiye` FROM `uyeler` WHERE `id` = 1 /*1)Fiyatı Al (1 yerine kartı basan kişinin idsi) */
/*3) Eklenen bakiyeye eski bakiye eklenir ve güncel bakiye elde edilip veitabanında güncellenir  bakiye=yenibakiye+bakiye 18.5=8.5+10 */
UPDATE `uyeler` SET`bakiye`= 18.5 WHERE `id` = 1 /*4)Yeni bakiye uyeler tablosundan güncellenir*/


/*Karta Para Yükleme mysql Kodları*/

/*Giriş Mysql kodları*/

SELECT * FROM `uyeler` WHERE `kart_no` = 101010 AND `sifre` = 123456 /*1)Böyle biri varsa bilgileri al */

/*Giriş Mysql kodları*/


/* Kayıt ol Mysql Kodları*/

INSERT INTO `uyeler` (`id`, `kart_no`, `adi`, `soyadi`, `sifre`, `il_id`, `bakiye`,`tur`) VALUES(1, 101010, 'burak', 'öner', '123456', '1', 10,`Ogrenci`);

/* Kayıt ol Mysql Kodları*/

/* Giriş Sayfası Mysql Kodları*/

SELECT * FROM `uyeler` WHERE `id` = 1 

/* Giriş Sayfası Mysql Kodları*/

