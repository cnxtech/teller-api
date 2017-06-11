<?php

namespace Teller;

class Teller
{
	public static $account;
	public static $personalAccessToken;

	public static function setPersonalAccessToken($token)
	{
		self::$personalAccessToken = $token;
	}

	public static function getPersonalAccessToken()
	{
		return self::$personalAccessToken;
	}

	public static function setAccount($uuid)
	{
		self::$account = $uuid;
	}

	public static function getAccounts()
	{
		return json_decode(self::_call('/accounts'));
	}

	public static function getAccount($uuid = NULL)
	{
		if (NULL === $uuid) {
			$uuid = self::$account;
		}
		return json_decode(self::_call('/accounts/' . $uuid));
	}

	public static function getTransactions($uuid = NULL)
	{
		if (NULL === $uuid) {
			$uuid = self::$account;
		}
		return json_decode(self::_call('/accounts/' . $uuid . '/transactions'));
	}

	public static function getTransaction($uuid, $account_uuid = null)
	{
		if (NULL === $account_uuid) {
			$account_uuid = self::$account;
		}
		return json_decode(self::_call('/accounts/' . $account_uuid . '/transactions/' . $uuid));
	}

	public static function getStandingOrders($uuid = NULL)
	{
		if (NULL === $uuid) {
			$uuid = self::$account;
		}
		return json_decode(self::_call('/accounts/' . $uuid . '/standing_orders'));
	}

	public static function getPayees($uuid = NULL)
	{
		if (NULL === $uuid) {
			$uuid = self::$account;
		}

		return json_decode(self::_call('/accounts/' . $uuid . '/payees'));
	}

	public static function getPayee($uuid, $account_uuid = null)
	{
		if (NULL === $account_uuid) {
			$account_uuid = self::$account;
		}

		return json_decode(self::_call('/accounts/' . $account_uuid . '/payees/' . $uuid));
	}

	public static function getDirectDebit($uuid, $account_uuid = null)
	{
		if (NULL === $account_uuid) {
			$account_uuid = self::$account;
		}

		return json_decode(self::_call('/accounts/' . $account_uuid . '/direct_debits/' . $uuid));
	}

	public static function getDirectDebits($uuid = null)
	{
		if (NULL === $uuid) {
			$uuid = self::$account;
		}
		return json_decode(self::_call('/accounts/' . $uuid . '/direct_debits'));
	}

	public static function _call($url = null)
	{
		$http = new \GuzzleHttp\Client();
		return $http->request(
			'GET',
			'https://api.teller.io' . $url,
			[
				'headers' =>
					[
						'Authorization' => "Bearer " . self::$personalAccessToken
					]
			]
		)->getBody()->getContents();
	}

}